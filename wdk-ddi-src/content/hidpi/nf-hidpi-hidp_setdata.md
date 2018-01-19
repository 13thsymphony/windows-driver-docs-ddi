---
UID : NF:hidpi.HidP_SetData
title : HidP_SetData function
author : windows-driver-content
description : The HidP_SetData routine sets a specified set of HID control button and value usages in a HID report.
old-location : hid\hidp_setdata.htm
old-project : hid
ms.assetid : 41f7c240-4e50-4d6c-82aa-902ab05bf715
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : HidP_SetData
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : hidpi.h
req.include-header : Hidpi.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : HidP_SetData
req.alt-loc : Hidparse.lib,Hidparse.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Hidparse.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : HIDP_REPORT_TYPE
---


# HidP_SetData function
The <b>HidP_SetData</b> routine sets a specified set of HID control button and value usages in a HID report.

## Syntax

````
NTSTATUS __stdcall HidP_SetData(
  _In_    HIDP_REPORT_TYPE     ReportType,
  _Inout_ PHIDP_DATA           DataList,
  _Inout_ PULONG               DataLength,
  _In_    PHIDP_PREPARSED_DATA PreparsedData,
  _In_    PCHAR                Report,
  _In_    ULONG                ReportLength
);
````

## Parameters

`ReportType`

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator value that indicates the type of HID report located at <i>Report</i>.

`DataList`

Pointer to a caller-allocated array of <a href="..\hidpi\ns-hidpi-_hidp_data.md">HIDP_DATA</a> structures that specify which buttons and usage values to set.

`DataLength`

Specifies, on input, the number of members in the <i>DataList</i> array. For information about the output value, see the Remarks section.

`PreparsedData`

Pointer to a top-level's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.

`Report`

Pointer to a HID report.

`ReportLength`

Specifies the size, in bytes, of the HID report located at <i>Report</i>, which must be equal to the report length for the specified report type that <a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a> returns in a collection's <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure.


## Return Value

<b>HidP_SetData</b> returns HIDP_STATUS_SUCCESS if it successfully sets all the control data specified by <i>DataList</i>.

<b>HidP_SetData</b> returns one of the following status values if one of the input parameters is not valid:
<dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl>The preparsed data specified by <i>PreparsedData</i> is not valid.
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_LENGTH</b></dt>
</dl>The size, in bytes, of the HID report is not equal to the length specified in the collection's <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure for the specified report type.
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_TYPE</b></dt>
</dl><i>ReportType</i> is not valid.
<dl>
<dt><b>HIDP_STATUS_REPORT_DOES_NOT_EXIST</b></dt>
</dl>The collection does not contain a report of the specified type.

 

HidP_SetData returns one of the following error values if one of the specified button or usage values could not be set:
<dl>
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>A button in an array was not set to ON (1) because all the array fields are already used to index other buttons.

<dl>
<dt><b>HIDP_STATUS_BUTTON_NOT_PRESSED</b></dt>
</dl>A DataList member specifies to set a button OFF (zero), but the button is already set to OFF.

<dl>
<dt><b>HIDP_STATUS_DATA_INDEX_NOT_FOUND</b></dt>
</dl>The data index of a DataList member is not valid.
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>A button or usage value is contained in a report, but it is not in the specified report.

<dl>
<dt><b>HIDP_STATUS_IS_VALUE_ARRAY</b></dt>
</dl>A data index specifies a <a href="hid.value_capability_arrays#usage_value_array#usage_value_array">usage value array</a>.

## Remarks

Except for usage value arrays, a user-mode application or kernel-mode driver can use <b>HidP_SetData</b> to set buttons and usage values in a report. To set a usage value array, an application or driver must use <a href="..\hidpi\nf-hidpi-hidp_setusagevaluearray.md">HidP_SetUsageValueArray</a>.

<b>HidP_SetData</b> sets the output value of <i>DataLength</i> as follows:



The input value is unchanged.

Set to the index of the <i>DataList</i> member that caused the error.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hidpi.h (include Hidpi.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>
</dt>
<dt>
<a href="..\hidpi\ns-hidpi-_hidp_data.md">HIDP_DATA</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_getdata.md">HidP_GetData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539779">HidP_SetButtons</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_setusages.md">HidP_SetUsages</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_setusagevaluearray.md">HidP_SetUsageValueArray</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539812">HidP_UnsetButtons</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_unsetusages.md">HidP_UnsetUsages</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_SetData routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>