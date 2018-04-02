---
UID: NF:fwpmk.FwpmCalloutAdd0
title: FwpmCalloutAdd0 function
author: windows-driver-content
description: The FwpmCalloutAdd0 function adds a callout to the filter engine.Note  FwpmCalloutAdd0 is a specific version of FwpmCalloutAdd.
old-location: netvista\fwpmcalloutadd0.htm
old-project: netvista
ms.assetid: f88a31c4-f42c-487d-b6d8-f8f609f2faff
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: FwpmCalloutAdd0, FwpmCalloutAdd0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmCalloutAdd0, netvista.fwpmcalloutadd0, wfp_ref_2_funct_2_fwpm_b1548682-4f29-467f-916d-fa434260b0ae.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpmk.h
req.include-header: Fwpmk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpmCalloutAdd0
product: Windows
targetos: Windows
req.typenames: INSTANCE_PARTIAL_INFORMATION, PINSTANCE_PARTIAL_INFORMATION
---


# FwpmCalloutAdd0 function
The 
  <b>FwpmCalloutAdd0</b> function adds a callout to the filter engine.
<div class="alert"><b>Note</b>  <b>FwpmCalloutAdd0</b> is a specific version of <b>FwpmCalloutAdd</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax

```
NTSTATUS FwpmCalloutAdd0(
  HANDLE               engineHandle,
  const FWPM_CALLOUT0  *callout,
  PSECURITY_DESCRIPTOR sd,
  UINT32               *id
);
```

## Parameters

`engineHandle`

A handle for an open session to the filter engine. A callout driver calls the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff550075">FwpmEngineOpen0</a> function to open a
     session to the filter engine.

`callout`

A pointer to a constant 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff550076">FWPM_CALLOUT0</a> structure that contains the
     data that is required to add the callout to the filter engine.

`sd`

A pointer to a constant <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a> structure that describes the security descriptor for
     the callout that is being added to the filter engine. This parameter is optional and can be <b>NULL</b>.

`id`

A pointer to a UINT32-typed variable that receives a run-time identifier that identifies the
     callout in the filter engine. This is the same identifier that is returned when a callout driver
     registers the callout driver's callout functions with the filter engine. The callout driver passes this
     identifier to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff550069">FwpmCalloutDeleteById0</a> function
     when removing the callout from the filter engine. This parameter is optional and can be <b>NULL</b>.


## Return Value

The 
     <b>FwpmCalloutAdd0</b> function returns one of the following NTSTATUS codes:

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
The callout was successfully added to the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_ALREADY_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
The callout could not be added to the filter engine. A callout already exists in the filter
       engine with an identifier identical to the GUID specified in the 
       <b>calloutKey</b> member of the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff550076">FWPM_CALLOUT0</a> structure pointed to by the 
       <i>callout</i> parameter.

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

A callout driver calls the 
    <b>FwpmCalloutAdd0</b> function to add a callout to the filter engine.

Callout drivers do not typically add their callouts to the filter engine. In most situations this is
    handled by a user-mode Windows Filtering Platform management application.

A callout and filters that specify the callout for the filter's action can be added to the filter
    engine before a callout driver registers the callout with the filter engine. In this situation, filters
    with an action type of <b>FWP_ACTION_CALLOUT_TERMINATING</b> or <b>FWP_ACTION_CALLOUT_UNKNOWN</b> are treated as
    <b>FWP_ACTION_BLOCK</b> and filters with an action type of <b>FWP_ACTION_CALLOUT_INSPECTION</b> are ignored until the
    callout is registered with the filter engine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista.  |
| **Target Platform** | Universal |
| **Header** | fwpmk.h (include Fwpmk.h) |
| **Library** | Fwpkclnt.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550076">FWPM_CALLOUT0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550069">FwpmCalloutDeleteById0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550071">FwpmCalloutDeleteByKey0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550075">FwpmEngineOpen0</a>



<a href="https://msdn.microsoft.com/d9539403-7657-4e95-8791-309673d1207d">Types of Callouts</a>