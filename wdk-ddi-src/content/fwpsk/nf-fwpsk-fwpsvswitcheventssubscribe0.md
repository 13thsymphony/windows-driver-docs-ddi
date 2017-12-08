---
UID: NF.fwpsk.FwpsvSwitchEventsSubscribe0
title: FwpsvSwitchEventsSubscribe0 function
author: windows-driver-content
description: The FwpsvSwitchEventsSubscribe0 function registers callback entry points for virtual switch layer events such as virtual port creation and deletion.Note  FwpsvSwitchEventsSubscribe0 is a specific version of FwpsvSwitchEventsSubscribe.
old-location: netvista\fwpsvswitcheventssubscribe0.htm
old-project: netvista
ms.assetid: 479ff048-f57f-42ca-8787-f87ed055fdbf
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: FwpsvSwitchEventsSubscribe0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsvSwitchEventsSubscribe0
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
req.irql: <= PASSIVE_LEVEL
---

# FwpsvSwitchEventsSubscribe0 function



## -description
The <b>FwpsvSwitchEventsSubscribe0</b> function registers callback entry points for virtual switch  layer events such as virtual port creation and deletion.<div class="alert"><b>Note</b>  <b>FwpsvSwitchEventsSubscribe0</b> is a specific version of <b>FwpsvSwitchEventsSubscribe</b>. See <a href="fwp.wfp_version-independent_names_and_targeting_specific_versions_of_windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -syntax

````
NTSTATUS NTAPI FwpsvSwitchEventsSubscribe0(
   _In_opt_ const GUID                          *providerGuid,
   _In_opt_ void                                *notifyContext,
   _In_ _Reserved_ UINT32                       flags,
   _In_ _Reserved_ void                         *reserved,
   _In_ const FWPS_VSWITCH_EVENT_DISPATCH_TABLE *eventDispatchTable,
   _Out_ UINT32                                 *subscriptionId
);
````


## -parameters

### -param providerGuid 

The provider GUID.



### -param notifyContext 

An optional pointer to a callout driver–supplied context. Event notification functions  pass this parameter back to the driver.

### -param flags 

Reserved. Set to zero.

### -param reserved 

Reserved. Set to zero.

### -param eventDispatchTable 

A pointer to an <a href="netvista.fwps_vswitch_event_dispatch_table0">FWPS_VSWITCH_EVENT_DISPATCH_TABLE</a> structure that defines the callback entry points for virtual switch layer events.

### -param subscriptionId 

A pointer to a variable that contains a unique identifier that WFP assigns to the subscription. The caller must return the subscription identifier to WFP with the  <a href="netvista.fwpsvswitcheventsunsubscribe0">FwpsvSwitchEventsUnsubscribe0</a> function.

## -returns
The 
     <b>FwpsvSwitchEventsSubscribe0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>A handle to the classify request was successfully returned. The variable that the 
       <i>classifyHandle</i> parameter points to contains the handle for the classify request.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 

## -remarks
A callout driver calls the <b>FwpsvSwitchEventsSubscribe0</b> function to register callback entry points for virtual switch  layer events.

The entry points for the callback notification functions are specified in and <a href="netvista.fwps_vswitch_event_dispatch_table0">FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</a> structure. 

The callout driver must later call 
    <a href="netvista.fwpsvswitcheventsunsubscribe0">FwpsvSwitchEventsUnsubscribe0</a>  to
    free the system resources.

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
Available starting with Windows 8.
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
&lt;= PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.fwps_vswitch_event_dispatch_table0">FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</a>
</dt>
<dt>
<a href="netvista.fwpsvswitcheventsunsubscribe0">FwpsvSwitchEventsUnsubscribe0</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsvSwitchEventsSubscribe0 function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
