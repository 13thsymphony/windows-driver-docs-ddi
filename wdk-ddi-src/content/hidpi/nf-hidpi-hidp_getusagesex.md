---
UID: NF:hidpi.HidP_GetUsagesEx
title: HidP_GetUsagesEx function
author: windows-driver-content
description: The HidP_GetUsagesEx routine returns a list of the all the HID control button usages that are set to ON in a HID report.
old-location: hid\hidp_getusagesex.htm
old-project: hid
ms.assetid: c799ecb6-3024-491c-90d5-70e1d21b1baf
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: HidP_GetUsagesEx
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
req.alt-api: HidP_GetUsagesEx
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
req.typenames: HIDP_REPORT_TYPE
---

# HidP_GetUsagesEx function



## -description
The <b>HidP_GetUsagesEx</b> routine returns a list of the all the HID control button <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usages</a> that are set to ON in a HID report. 



## -syntax

````
NTSTATUS __stdcall HidP_GetUsagesEx(
  _In_    HIDP_REPORT_TYPE     ReportType,
  _In_    USHORT               LinkCollection,
  _Inout_ PUSAGE_AND_PAGE      ButtonList,
  _Inout_ ULONG                *UsageLength,
  _In_    PHIDP_PREPARSED_DATA PreparsedData,
  _In_    PCHAR                Report,
  _In_    ULONG                ReportLength
);
````


## -parameters

### -param ReportType [in]

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.


### -param LinkCollection [in]

Specifies the <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a> of the button usages. If <i>LinkCollection</i> is nonzero, the routine only returns information about the buttons that this link collection contains; otherwise, if <i>LinkCollection</i> is zero, the routine returns information about all the buttons in the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> associated with <i>PreparsedData</i>.


### -param ButtonList [in, out]

Pointer to a caller-allocated buffer that routine uses to return the usage and <a href="hid.hid_usages#usage_page#usage_page">usage page</a> identifiers for each button that is set to ON (1).


### -param UsageLength [in, out]

Specifies, on input, the length, in array elements, of the <i>ButtonList</i> buffer. Specifies, on output, the number usages that are currently set to ON in the specified report.


### -param PreparsedData [in]

Pointer to a top-level collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


### -param Report [in]

Pointer to a report that contains button data.


### -param ReportLength [in]

Specifies the length, in bytes, of the report located at <i>Report</i>.


## -returns
<b>HidP_GetUsagesEx</b> returns one of the following status values:
<dl>
<dt><b>HIDP_STATUS_SUCCESS</b></dt>
</dl>The routine successfully returned all button usages set to ON.
<dl>
<dt><b>HIDP_INVALID_REPORT_LENGTH</b></dt>
</dl>The report length is not valid.
<dl>
<dt><b>HIDP_INVALID_REPORT_TYPE</b></dt>
</dl>The specified report type is not valid.
<dl>
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The <i>UsageList</i> buffer is too small to hold all the usages currently set to ON in the specified report.
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>The collection contains buttons in a report of the specified type, but there are no such usages in the specified report.
<dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl>The preparsed data is not valid.

 


## -remarks
User-mode applications and kernel-mode drivers call <a href="..\hidpi\nf-hidpi-hidp_maxusagelistlength.md">HidP_MaxUsageListLength</a> to determine the maximum number of buttons that be returned for specified report type. Alternatively, applications or drivers can call <b>HidP_GetUsagesEx</b> and set <i>UsageList </i>to zero to return the required length in <i>UsageLength</i>.

Applications or drivers determine the required report length from the <i>Xxx</i><b>ReportByteLength</b> members in a top-level collection's <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539712">HidP_GetButtonsEx</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_getscaledusagevalue.md">HidP_GetScaledUsageValue</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_getusagesex.md">HidP_GetUsagesEx</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_getusagevalue.md">HidP_GetUsageValue</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_getusagevaluearray.md">HidP_GetUsageValueArray</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_maxusagelistlength.md">HidP_MaxUsageListLength</a>
</dt>
<dt>
<a href="..\hidpi\ns-hidpi-_usage_and_page.md">USAGE_AND_PAGE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_GetUsagesEx routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

