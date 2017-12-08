---
UID: NF.fwpsk.FwpsNetBufferListAssociateContext0
title: FwpsNetBufferListAssociateContext0 function
author: windows-driver-content
description: The FwpsNetBufferListAssociateContext0 function associates the callout driver's context with a network buffer list and configures notification for network buffer list events.Note  FwpsNetBufferListAssociateContext0 is the specific version of FwpsNetBufferListAssociateContext used in Windows 7 and later. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information. For Windows 8, FwpsNetBufferListAssociateContext1 is available.
old-location: netvista\fwpsnetbufferlistassociatecontext0.htm
old-project: netvista
ms.assetid: 31135396-303b-4b94-8616-a4b7be207fa1
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: FwpsNetBufferListAssociateContext0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsNetBufferListAssociateContext0
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
---

# FwpsNetBufferListAssociateContext0 function



## -description
The 
  <b>FwpsNetBufferListAssociateContext0</b> function associates the callout driver's context with a network buffer
  list and configures notification for network buffer list events.


## -syntax

````
NTSTATUS NTAPI FwpsNetBufferListAssociateContext0(
  _Inout_ NET_BUFFER_LIST                 *netBufferList,
  _In_    UINT16                          layerId,
  _In_    UINT64                          context,
  _In_    UINT64                          contextTag,
  _In_    GUID                            *providerGUID,
  _Inout_ void                            *deviceObject,
  _In_    FWPS_NET_BUFFER_LIST_NOTIFY_FN0 notifyFn,
  _In_    UINT32                          flags
);
````


## -parameters

### -param netBufferList [in, out]

A network buffer list that indicates one or more packets of interest to the callout driver.

### -param layerId [in]

The identifier of the layer in which the context is being associated. When calling this function
     from the NDIS receive path, set this parameter to FWPS_LAYER_NON_WFP.

### -param context [in]

Arbitrary context information set by the callout driver. The filter engine will pass this context
     to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_net_buffer_list_notify_fn0.md">
     FWPS_NET_BUFFER_LIST_NOTIFY_FN0</a>.

### -param contextTag [in]

A locally unique identifier obtained by calling the 
     <a href="netvista.fwpsnetbufferlistgettagforcontext0">
     FwpsNetBufferListGetTagForContext0</a> function.

### -param providerGUID [in]

The provider GUID.

### -param deviceObject [in, out]

A pointer to the callout driver's device object.

### -param notifyFn [in]

A pointer to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_net_buffer_list_notify_fn0.md">
     FWPS_NET_BUFFER_LIST_NOTIFY_FN0</a> function. The filter engine will send status notifications to this
     function.

### -param flags [in]

This parameter is reserved for future use and is set to zero.

## -returns
The 
     <b>FwpsNetBufferListAssociateContext0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The association was successful.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 

## -remarks
The 
    <b>FwpsNetBufferListAssociateContext0</b> function associates groups of packets with the callout driver.
    Packets of interest can be tracked for inspection through multiple layers in the stack.

Before calling this function, the 
    <a href="netvista.fwpsnetbufferlistgettagforcontext0">FwpsNetBufferListGetTagForContext0</a> function must be called to obtain a context tag.

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
Available starting with  Windows 7.
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
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="netvista.fwpsnetbufferlistassociatecontext1">FwpsNetBufferListAssociateContext1</a>
</dt>
<dt>
<a href="netvista.fwpsnetbufferlistgettagforcontext0">
   FwpsNetBufferListGetTagForContext0</a>
</dt>
<dt>
<a href="netvista.fwpsnetbufferlistremovecontext0">
   FwpsNetBufferListRemoveContext0</a>
</dt>
<dt>
<a href="netvista.fwpsnetbufferlistretrievecontext0">
   FwpsNetBufferListRetrieveContext0</a>
</dt>
<dt>
<a href="netvista.using_packet_tagging">Using Packet Tagging</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsNetBufferListAssociateContext0 function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
