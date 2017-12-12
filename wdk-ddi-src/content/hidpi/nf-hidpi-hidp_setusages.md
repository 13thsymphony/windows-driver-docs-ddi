---
UID: NF.hidpi.HidP_SetUsages
title: HidP_SetUsages function
author: windows-driver-content
description: The HidP_SetUsages routine sets specified HID control buttons ON (1) in a HID report.
old-location: hid\hidp_setusages.htm
old-project: hid
ms.assetid: a9f229cd-33ca-42b5-bae6-3f367e5f1e84
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: HidP_SetUsages
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
req.alt-api: HidP_SetUsages
req.alt-loc: Hidparse.lib,Hidparse.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hidparse.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# HidP_SetUsages function



## -description
The <b>HidP_SetUsages</b> routine sets specified HID control buttons ON (1) in a HID report.



## -syntax

````
NTSTATUS __stdcall HidP_SetUsages(
  _In_    HIDP_REPORT_TYPE     ReportType,
  _In_    USAGE                UsagePage,
  _In_    USHORT               LinkCollection,
  _Inout_ PUSAGE               UsageList,
  _Inout_ PULONG               UsageLength,
  _In_    PHIDP_PREPARSED_DATA PreparsedData,
  _In_    PCHAR                Report,
  _In_    ULONG                ReportLength
);
````


## -parameters

### -param ReportType [in]

Specifies a <a href="hid.hidp_report_type">HIDP_REPORT_TYPE</a> enumerator value that indicates the type of report located at <i>Report</i>.


### -param UsagePage [in]

Specifies the <a href="hid.hid_usages#usage_page#usage_page">usage page</a> for the usages specified by <i>UsageList</i>.


### -param LinkCollection [in]

Specifies the <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a> that contains the usages. If <i>LinkCollection</i> is nonzero, the routine only sets the usages, if they exist, in this link collection. If <i>LinkCollection</i> is zero, the routine sets the first usage for each specified usage in the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> associated with <i>PreparsedData</i>.


### -param UsageList [in, out]

Pointer to the array of usages.


### -param UsageLength [in, out]

Specifies, on input, the number of usages in <i>UsageList</i>. See the Remarks section for information about the output value.


### -param PreparsedData [in]

Pointer to the <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a> of the top-level collection associated with the report located at <i>Report</i>.


### -param Report [in]

Pointer to a report.


### -param ReportLength [in]

Specifies the size, in bytes, of the report located at <i>Report</i>, which must be equal to the report length for the specified report type that <a href="hid.hidp_getcaps">HidP_GetCaps</a> returns in a collection's <a href="hid.hidp_caps">HIDP_CAPS</a> structure.


## -returns
<b>HidP_SetUsages</b> returns one of the following status values:
<dl>
<dt><b>HIDP_STATUS_SUCCESS</b></dt>
</dl>The routine successfully set the usage value.
<dl>
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>A usage in a button array cannot be set because the array is already fully set.
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_LENGTH</b></dt>
</dl>The report length is not valid.
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_TYPE</b></dt>
</dl>The specified report type is not valid.
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>A usage does not exist in the specified report, but it does exist in a different report of the specified type.
<dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl>The preparsed data is not valid.
<dl>
<dt><b>HIDP_STATUS_USAGE_NOT_FOUND</b></dt>
</dl>A usage does not exist in any report of the specified report type.

 


## -remarks
If <b>HidP_SetUsages</b> cannot set a usage in <i>UsageList</i>, the routine sets <i>UsageLength</i> to the index of the usage that could not be set, and returns a status value that indicates the error.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


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
Available in Windows 2000 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hidpi.h (include Hidpi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Hidparse.lib</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543586">_HIDP_PREPARSED_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539708">HidP_GetButtons</a>
</dt>
<dt>
<a href="hid.hidp_getusages">HidP_GetUsages</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539779">HidP_SetButtons</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539812">HidP_UnsetButtons</a>
</dt>
<dt>
<a href="hid.hidp_unsetusages">HidP_UnsetUsages</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_SetUsages routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

