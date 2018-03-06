---
UID: NF:fwpsk.FwpsFlowAbort0
title: FwpsFlowAbort0 function
author: windows-driver-content
description: The FwpsFlowAbort0 function aborts a data flow.Note  FwpsFlowAbort0 is a specific version of FwpsFlowAbort.
old-location: netvista\fwpsflowabort0.htm
old-project: netvista
ms.assetid: 029dd387-498f-4402-9e61-a46688294949
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: FwpsFlowAbort0, FwpsFlowAbort0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsFlowAbort0, netvista.fwpsflowabort0
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsFlowAbort0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---


# FwpsFlowAbort0 function
The <b>FwpsFlowAbort0</b> function aborts a data flow.<div class="alert"><b>Note</b>  <b>FwpsFlowAbort0</b> is a specific version of <b>FwpsFlowAbort</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>

## Syntax

````
NTSTATUS NTAPI FwpsFlowAbort0(
  _In_ UINT64 flowId
);
````

## Parameters

`flowId`

A run-time identifier that specifies the data flow that is being aborted. The run-time identifier for a data flow is provided to a callout driver through the FWPS_METADATA_FIELD_FLOW_HANDLE metadata value that the filter engine provided to the callout driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function.


## Return Value

The 
     <b>FwpsFlowAbort0</b> function returns one of the following NTSTATUS codes.

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
The flow was aborted. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>

## Remarks

A callout driver can call the <b>FwpsFlowAbort0</b> function to abort a data flow. 
   The filter engine calls the 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a> callout function when the flow is terminated so that the callout driver can clean up
    the context associated with the flow.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** | Fwpkclnt.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsFlowAbort0 function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>