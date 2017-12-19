---
UID: NC.fwpsk.FWPS_CALLOUT_NOTIFY_FN2
title: FWPS_CALLOUT_NOTIFY_FN2
author: windows-driver-content
description: The filter engine calls a callout's notifyFn2 callout function to notify the callout driver about events that are associated with the callout.Note  notifyFn2 is the specific version of notifyFn used in Windows 8 and later.
old-location: netvista\notifyfn2.htm
old-project: NetVista
ms.assetid: c70c987b-5b4c-4ddd-8eb8-8c3c40003ab3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FwpmEngineOpen0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: notifyFn2
req.alt-loc: Fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# FWPS_CALLOUT_NOTIFY_FN2 callback



## -description
The filter engine calls a callout's 
  <i>notifyFn2</i> callout function to notify the callout driver about events that are associated with the
  callout.<div class="alert"><b>Note</b>  <i>notifyFn2</i> is the specific version of <a href="netvista.notifyfn">notifyFn</a> used in Windows 8 and later. See <a href="fwp.wfp_version-independent_names_and_targeting_specific_versions_of_windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 7, <a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn1.md">notifyFn1</a> is available. For Windows Vista, <a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn0.md">notifyFn0</a> is available.</div>
<div> </div>




## -prototype

````
FWPS_CALLOUT_NOTIFY_FN2 notifyFn2;

NTSTATUS NTAPI notifyFn2(
  _In_          FWPS_CALLOUT_NOTIFY_TYPE notifyType,
  _In_    const GUID                     *filterKey,
  _Inout_       FWPS_FILTER2             *filter
)
{ ... }
````


## -parameters

### -param notifyType [in]

A value that indicates the type of notification that the filter engine is sending to the callout.
     Valid values for this parameter are:
     




### -param FWPS_CALLOUT_NOTIFY_ADD_FILTER

A filter is being added to the filter engine that specifies the callout for the filter's
       action.


### -param FWPS_CALLOUT_NOTIFY_DELETE_FILTER

A filter is being deleted from the filter engine that specifies the callout for the filter's
       action.


### -param FWPS_CALLOUT_NOTIFY_TYPE_MAX

A maximum value for testing purposes.

</dd>
</dl>

### -param filterKey [in]

A pointer to the management identifier for the filter, as specified by the application or driver
     that is adding or deleting the filter. Must be NULL if the 
     <i>notifyType</i> parameter is set to FWPS_CALLOUT_NOTIFY_DELETE_FILTER. For more information, see the
     following Remarks section.


### -param filter [in, out]

A pointer to an 
     <a href="netvista.fwps_filter2">FWPS_FILTER2</a> structure. This structure
     describes the filter that is being added to or deleted from the filter engine.
     

A callout driver's 
     <i>notifyFn2</i> function can set the 
     <b>Context</b> member of this structure to point to a callout driver-supplied context structure when the
     filter is added to the filter engine. This context structure is opaque to the filter engine, and can be
     used by the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn2.md">classifyFn2</a> callout function to preserve
     any driver-specific data or state information between calls by the filter engine to the callout driver's
     
     <i>classifyFn2</i> callout function.

A callout driver's 
     <i>notifyFn2</i> function can clean up any context associated with the filter when the filter is deleted
     from the filter engine.


## -returns
A callout's 
     <i>notifyFn2</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The callout driver accepts the notification from the filter engine.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. If the 
       <i>notifyType</i> parameter is FWPS_CALLOUT_NOTIFY_ADD_FILTER, the filter will not be added to the
       filter engine. If the 
       <i>notifyType</i> parameter is FWPS_CALLOUT_NOTIFY_DELETE_FILTER, the filter will still be deleted from
       the filter engine.

 


## -remarks
A callout driver registers a callout's callout functions with the filter engine by calling the 
    <a href="netvista.fwpscalloutregister2">FwpsCalloutRegister2</a> function.

The filter engine calls a callout driver's 
    <i>notifyFn2</i> function to notify the callout driver about events that are associated with the callout.
    If the callout driver's 
    <i>notifyFn2</i> function does not recognize the type of notification that is passed in the 
    <i>notifyType</i> parameter, it should ignore the notification and return STATUS_SUCCESS.

If a callout driver registers a callout with the filter engine after filters that specify the callout
    for the filter's action have already been added to the filter engine, the filter engine does not call the
    callout driver's 
    <i>notifyFn2</i> function to notify the callout about any of the existing filters. The filter engine calls
    the callout driver's 
    <i>notifyFn2</i> function to notify the callout when new filters that specify the callout for the filter's
    action are added to the filter engine. In this situation, a callout's 
    <i>notifyFn2</i> function might not get called for every filter in the filter engine that specifies the
    callout for the filter's action. If a callout driver registers a callout after the filter engine is
    started and the callout needs to know about every filter in the filter engine that specifies the callout
    for the filter's action, the callout driver must call the appropriate management functions to enumerate
    all the filters in the filter engine and sort through the resulting list of filters to find those that
    specify the callout for the filter's action. See 
    <a href="netvista.calling_other_windows_filtering_platform_functions">Calling Other
    Windows Filtering Platform Functions</a> for more information about calling these functions.

When a filter that specifies a callout for the filter's action is deleted from the filter engine, the
    filter engine calls the callout driver's 
    <i>notifyFn2</i> function and passes FWP_CALLOUT_NOTIFY_DELETE_FILTER in the 
    <i>notifyType</i> parameter and NULL in the 
    <i>filterKey</i> parameter. For more information, see 
    <a href="netvista.processing_notify_callouts">Processing Notify Callouts</a>.

This function is essentially identical to the previous version, 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn1.md">notifyFn1</a>. The only difference is the 
       updated <a href="netvista.fwps_filter2">FWPS_FILTER2</a> structure pointed to by the 
       <i>filter</i> parameter.


## -requirements
<table>
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
<a href="netvista.fwps_filter2">FWPS_FILTER2</a>
</dt>
<dt>
<a href="netvista.fwpscalloutregister2">FwpsCalloutRegister2</a>
</dt>
<dt>
<a href="netvista.notifyfn">notifyFn</a>
</dt>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn0.md">notifyFn0</a>
</dt>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn1.md">notifyFn1</a>
</dt>
<dt>
<a href="netvista.callout_driver_callout_functions">Callout Driver Callout Functions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20FWPS_CALLOUT_NOTIFY_FN2 callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

