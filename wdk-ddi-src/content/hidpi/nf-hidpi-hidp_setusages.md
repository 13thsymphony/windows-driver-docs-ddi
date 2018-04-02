---
UID: NF:hidpi.HidP_SetUsages
title: HidP_SetUsages function
author: windows-driver-content
description: The HidP_SetUsages routine sets specified HID control buttons ON (1) in a HID report.
old-location: hid\hidp_setusages.htm
old-project: hid
ms.assetid: a9f229cd-33ca-42b5-bae6-3f367e5f1e84
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HidP_SetUsages, HidP_SetUsages routine [Human Input Devices], hid.hidp_setusages, hidfunc_4d0213bb-2715-446b-bdaf-f82be3cbc11b.xml, hidpi/HidP_SetUsages
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hidpi.h
req.include-header: Hidpi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hidparse.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hidparse.lib
-	Hidparse.dll
api_name:
-	HidP_SetUsages
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---


# HidP_SetUsages function
The <b>HidP_SetUsages</b> routine sets specified HID control buttons ON (1) in a HID report.

## Syntax

```
NTSTATUS HidP_SetUsages(
  HIDP_REPORT_TYPE     ReportType,
  USAGE                UsagePage,
  USHORT               LinkCollection,
  PUSAGE               UsageList,
  PULONG               UsageLength,
  PHIDP_PREPARSED_DATA PreparsedData,
  PCHAR                Report,
  ULONG                ReportLength
);
```

## Parameters

`ReportType`

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539774">HIDP_REPORT_TYPE</a> enumerator value that indicates the type of report located at <i>Report</i>.

`UsagePage`

Specifies the <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage page</a> for the usages specified by <i>UsageList</i>.

`LinkCollection`

Specifies the <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a> that contains the usages. If <i>LinkCollection</i> is nonzero, the routine only sets the usages, if they exist, in this link collection. If <i>LinkCollection</i> is zero, the routine sets the first usage for each specified usage in the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> associated with <i>PreparsedData</i>.

`UsageList`

Pointer to the array of usages.

`UsageLength`

Specifies, on input, the number of usages in <i>UsageList</i>. See the Remarks section for information about the output value.

`PreparsedData`

Pointer to the <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a> of the top-level collection associated with the report located at <i>Report</i>.

`Report`

Pointer to a report.

`ReportLength`

Specifies the size, in bytes, of the report located at <i>Report</i>, which must be equal to the report length for the specified report type that <a href="https://msdn.microsoft.com/library/windows/hardware/ff539715">HidP_GetCaps</a> returns in a collection's <a href="https://msdn.microsoft.com/library/windows/hardware/ff539697">HIDP_CAPS</a> structure.


## Return Value

<b>HidP_SetUsages</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The routine successfully set the usage value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
A usage in a button array cannot be set because the array is already fully set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_LENGTH</b></dt>
</dl>
</td>
<td width="60%">
The report length is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_TYPE</b></dt>
</dl>
</td>
<td width="60%">
The specified report type is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>
</td>
<td width="60%">
A usage does not exist in the specified report, but it does exist in a different report of the specified type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl>
</td>
<td width="60%">
The preparsed data is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_USAGE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
A usage does not exist in any report of the specified report type.

</td>
</tr>
</table>

## Remarks

If <b>HidP_SetUsages</b> cannot set a usage in <i>UsageList</i>, the routine sets <i>UsageLength</i> to the index of the usage that could not be set, and returns a status value that indicates the error.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | hidpi.h (include Hidpi.h) |
| **Library** | Hidparse.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539708">HidP_GetButtons</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539742">HidP_GetUsages</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539779">HidP_SetButtons</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539812">HidP_UnsetButtons</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539819">HidP_UnsetUsages</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>