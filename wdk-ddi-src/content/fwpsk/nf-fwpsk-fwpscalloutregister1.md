---
UID : NF:fwpsk.FwpsCalloutRegister1
title : FwpsCalloutRegister1 function
author : windows-driver-content
description : The FwpsCalloutRegister1 function registers a callout with the filter engine.Note  FwpsCalloutRegister1 is the specific version of FwpsCalloutRegister used in Windows 7 and later.
old-location : netvista\fwpscalloutregister1.htm
old-project : netvista
ms.assetid : 496e2206-56d1-47eb-a9e6-f5d4799e3dde
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : FwpsCalloutRegister1
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 7.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FwpsCalloutRegister1
req.alt-loc : Fwpkclnt.lib,Fwpkclnt.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Fwpkclnt.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : FWPS_VSWITCH_EVENT_TYPE
---


# FwpsCalloutRegister1 function
The 
  <b>FwpsCalloutRegister1</b> function registers a callout with the filter engine.

## Syntax

````
NTSTATUS NTAPI FwpsCalloutRegister1(
  _Inout_         void          *deviceObject,
  _In_      const FWPS_CALLOUT1 *callout,
  _Out_opt_       UINT32        *calloutId
);
````

## Parameters

`deviceObject`

A pointer to a device object that was previously created by the callout driver. For more
     information about how a callout driver creates a device object, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff542862">Creating a Device Object</a>.

`callout`

A pointer to a constant 
     <a href="..\fwpsk\ns-fwpsk-fwps_callout1_.md">FWPS_CALLOUT1</a> structure that contains the
     data that is required to register the callout with the filter engine.

`calloutId`

A pointer to a UINT32-typed variable that receives a run-time identifier that identifies the
     callout in the filter engine. The callout driver passes this identifier to the 
     <a href="..\fwpsk\nf-fwpsk-fwpscalloutunregisterbyid0.md">FwpsCalloutUnregisterById0</a> function when unregistering the callout from the filter engine. If a
     callout driver is filtering a data flow, it also passes this identifier to the 
     <a href="..\fwpsk\nf-fwpsk-fwpsflowassociatecontext0.md">FwpsFlowAssociateContext0</a> and 
     <a href="..\fwpsk\nf-fwpsk-fwpsflowremovecontext0.md">FwpsFlowRemoveContext0</a> functions.
     If a callout driver injects data into data streams, it also passes this identifier to the 
     <a href="..\fwpsk\nf-fwpsk-fwpsstreaminjectasync0.md">FwpsStreamInjectAsync0</a> function. 
     The filter engine also passes this
     identifier to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a> callout function. This
     parameter is optional and can be <b>NULL</b>.


## Return Value

The 
     <b>FwpsCalloutRegister1</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The callout was successfully registered with the filter engine.
<dl>
<dt><b>STATUS_FWP_ALREADY_EXISTS</b></dt>
</dl>The callout could not be registered with the filter engine. A callout is already registered in
       the filter engine with an identifier identical to the GUID specified in the 
       <b>calloutKey</b> member of the 
       <a href="..\fwpsk\ns-fwpsk-fwps_callout1_.md">FWPS_CALLOUT1</a> structure pointed to by the 
       <i>callout</i> parameter.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

## Remarks

A callout driver calls the 
    <b>FwpsCalloutRegister1</b> function to register a callout with the filter engine. A callout driver can
    register a callout with the filter engine at any time, even if the filter engine is not currently
    running.

A callout and filters that specify the callout for the filter's action can be added to the filter
    engine before a callout driver registers the callout with the filter engine. In this situation, filters
    with an action type of <b>FWP_ACTION_CALLOUT_TERMINATING</b> or <b>FWP_ACTION_CALLOUT_UNKNOWN</b> are treated as
    <b>FWP_ACTION_BLOCK</b>, and filters with an action type of <b>FWP_ACTION_CALLOUT_INSPECTION</b> are ignored until the
    callout is registered with the filter engine.

A callout driver unregisters a callout from the filter engine by calling either the 
    <a href="..\fwpsk\nf-fwpsk-fwpscalloutunregisterbyid0.md">
    FwpsCalloutUnregisterById0</a> function or the 
    <a href="..\fwpsk\nf-fwpsk-fwpscalloutunregisterbykey0.md">
    FwpsCalloutUnregisterByKey0</a> function. A callout driver cannot be unloaded until all of the callouts
    that were previously registered with the filter engine have been successfully unregistered.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\fwpsk\ns-fwpsk-fwps_callout1_.md">FWPS_CALLOUT1</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister2.md">FwpsCalloutRegister2</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscalloutunregisterbyid0.md">FwpsCalloutUnregisterById0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscalloutunregisterbykey0.md">FwpsCalloutUnregisterByKey0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsflowassociatecontext0.md">FwpsFlowAssociateContext0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsflowremovecontext0.md">FwpsFlowRemoveContext0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsstreaminjectasync0.md">FwpsStreamInjectAsync0</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a>
</dt>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/d9539403-7657-4e95-8791-309673d1207d">Types of Callouts</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsCalloutRegister1 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>