---
UID: NF:fwpsk.FwpsFlowAssociateContext0
title: FwpsFlowAssociateContext0 function
author: windows-driver-content
description: The FwpsFlowAssociateContext0 function associates a callout driver-defined context with a data flow.Note  FwpsFlowAssociateContext0 is a specific version of FwpsFlowAssociateContext.
old-location: netvista\fwpsflowassociatecontext0.htm
old-project: netvista
ms.assetid: 0a339457-77df-480b-adb8-9406507ec8d8
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: FwpsFlowAssociateContext0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsFlowAssociateContext0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsFlowAssociateContext0 function



## -description
The 
  <b>FwpsFlowAssociateContext0</b> function associates a callout driver-defined context with a data
  flow.



## -syntax

````
NTSTATUS NTAPI FwpsFlowAssociateContext0(
  _In_ UINT64 flowId,
  _In_ UINT16 layerId,
  _In_ UINT32 calloutId,
  _In_ UINT64 flowContext
);
````


## -parameters

### -param flowId [in]

A run-time identifier that specifies the data flow with which to associate the context. The
     run-time identifier for a data flow is provided to a callout driver through the
     FWPS_METADATA_FIELD_FLOW_HANDLE metadata value that was passed to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function.


### -param layerId [in]

The run-time identifier for the filtering layer with which the context is being associated. The context will be associated only with the specified filtering layer. For
     more information, see 
     <a href="netvista.run_time_filtering_layer_identifiers">Run-time Filtering Layer
     Identifiers</a>.


### -param calloutId [in]

The run-time identifier for the callout in the filter engine. This identifier was returned when
     the callout driver called the 
     <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a>, 
     <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister1.md">FwpsCalloutRegister1</a>, or  <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister2.md">FwpsCalloutRegister2</a> function to
     register the callout with the filter engine.


### -param flowContext [in]

The callout driver-defined context to be associated with the data flow. This parameter must not be
     zero. This context is opaque to the filter engine.


## -returns
The 
     <b>FwpsFlowAssociateContext0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The context was successfully associated with the data flow.
<dl>
<dt><b>STATUS_INVALID PARAMETER</b></dt>
</dl>Either the <i>flowContext</i> parameter is <b>NULL</b> or the callout specified by the <i>calloutID</i> parameter does not have a <a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a> registered.
<dl>
<dt><b>STATUS_OBJECT_NAME_EXISTS</b></dt>
</dl>A context is already associated with the data flow. In this case, a callout driver should first
       call the 
       <a href="..\fwpsk\nf-fwpsk-fwpsflowremovecontext0.md">FwpsFlowRemoveContext0</a> function
       to remove the existing context and then call the 
       <a href="..\fwpsk\nf-fwpsk-fwpsflowassociatecontext0.md">FwpsFlowAssociateContext0</a> function again to associate the new context with the data flow.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
When filtering a data flow, a callout driver can call the 
    <b>FwpsFlowAssociateContext0</b> function to associate a context with the data flow. It can then use this
    context to preserve any driver-specific data or state information between calls by the filter engine to a
    callout's 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function for that data
    flow.

There must be a callout in the filter engine at the layer identified by the 
    <i>layerId</i> parameter that has registered a 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a> callout function. Otherwise,
    the call to the 
    <b>FwpsFlowAssociateContext0</b> function will return STATUS_INVALID_PARAMETER. The filter engine calls that 
    <i>flowDeleteFn</i> callout function when the flow is terminated so that the callout driver can clean up
    the context associated with the flow.

You can call <b>FwpsFlowAssociateContext0</b> multiple times for the same flow. In each call, you must specify a different callout and a different context—one context per added callout.

The <b>FwpsFlowAssociateContext0</b> function associates a single context with a single added callout.

You can associate multiple contexts with a flow. However, each context must be associated with a different callout. The new callout can be at the same layer as the previous one or at a different layer.

For more information and sample code, see <a href="https://msdn.microsoft.com/75f5838e-626d-4a59-810e-fec9a40640ed">Associating Context with a Data Flow</a>
and the <a href="http://go.microsoft.com/fwlink/p/?LinkId=618934">Windows Filtering Platform Sample</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows Vista.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Fwpkclnt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>
</dt>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister1.md">FwpsCalloutRegister1</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister2.md">FwpsCalloutRegister2</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsflowremovecontext0.md">FwpsFlowRemoveContext0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/75f5838e-626d-4a59-810e-fec9a40640ed">Associating Context with a Data Flow</a>
</dt>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkId=618934">Windows Filtering Platform Sample</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsFlowAssociateContext0 function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

