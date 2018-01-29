---
UID : NC:fwpsk.FWPS_CALLOUT_NOTIFY_FN2
title : FWPS_CALLOUT_NOTIFY_FN2
author : windows-driver-content
description : The filter engine calls a callout's notifyFn2 callout function to notify the callout driver about events that are associated with the callout.Note  notifyFn2 is the specific version of notifyFn used in Windows 8 and later.
old-location : netvista\notifyfn2.htm
old-project : netvista
ms.assetid : c70c987b-5b4c-4ddd-8eb8-8c3c40003ab3
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.notifyfn2, notifyFn2 callback function [Network Drivers Starting with Windows Vista], notifyFn2, FWPS_CALLOUT_NOTIFY_FN2, FWPS_CALLOUT_NOTIFY_FN2, fwpsk/notifyFn2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PINSTANCE_PARTIAL_INFORMATION, INSTANCE_PARTIAL_INFORMATION
---


# FWPS_CALLOUT_NOTIFY_FN2 callback function
The filter engine calls a callout's 
  <i>notifyFn2</i> callout function to notify the callout driver about events that are associated with the
  callout.<div class="alert"><b>Note</b>  <i>notifyFn2</i> is the specific version of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568802">notifyFn</a> used in Windows 8 and later. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 7, <a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn1.md">notifyFn1</a> is available. For Windows Vista, <a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn0.md">notifyFn0</a> is available.</div>
<div> </div>

## Syntax

```
FWPS_CALLOUT_NOTIFY_FN2 FwpsCalloutNotifyFn2;

NTSTATUS FwpsCalloutNotifyFn2(
  FWPS_CALLOUT_NOTIFY_TYPE notifyType,
  const GUID *filterKey,
  FWPS_FILTER2 *filter
)
{...}
```

## Parameters

`notifyType`

A value that indicates the type of notification that the filter engine is sending to the callout.
     Valid values for this parameter are:

`*filterKey`



`*filter`




## Return Value

A callout's 
     <i>notifyFn2</i> function returns one of the following NTSTATUS codes.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The callout driver accepts the notification from the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. If the 
       <i>notifyType</i> parameter is FWPS_CALLOUT_NOTIFY_ADD_FILTER, the filter will not be added to the
       filter engine. If the 
       <i>notifyType</i> parameter is FWPS_CALLOUT_NOTIFY_DELETE_FILTER, the filter will still be deleted from
       the filter engine.

</td>
</tr>
</table>

## Remarks

A callout driver registers a callout's callout functions with the filter engine by calling the 
    <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister2.md">FwpsCalloutRegister2</a> function.

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
    <mshelp:link keywords="netvista.calling_other_windows_filtering_platform_functions" tabindex="0">Calling Other
    Windows Filtering Platform Functions</mshelp:link> for more information about calling these functions.

When a filter that specifies a callout for the filter's action is deleted from the filter engine, the
    filter engine calls the callout driver's 
    <i>notifyFn2</i> function and passes FWP_CALLOUT_NOTIFY_DELETE_FILTER in the 
    <i>notifyType</i> parameter and NULL in the 
    <i>filterKey</i> parameter. For more information, see 
    <a href="https://msdn.microsoft.com/d686989e-97f0-4095-b172-1c2ccf7a26e6">Processing Notify Callouts</a>.

This function is essentially identical to the previous version, 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn1.md">notifyFn1</a>. The only difference is the 
       updated <a href="https://msdn.microsoft.com/library/windows/hardware/hh439768">FWPS_FILTER2</a> structure pointed to by the 
       <i>filter</i> parameter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn0.md">notifyFn0</a>

<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister2.md">FwpsCalloutRegister2</a>

<a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn1.md">notifyFn1</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439768">FWPS_FILTER2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568802">notifyFn</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_CALLOUT_NOTIFY_FN2 callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>