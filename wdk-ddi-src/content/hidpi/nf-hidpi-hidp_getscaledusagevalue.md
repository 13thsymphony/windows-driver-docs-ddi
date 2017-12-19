---
UID: NF.hidpi.HidP_GetScaledUsageValue
title: HidP_GetScaledUsageValue function
author: windows-driver-content
description: The HidP_GetScaledUsageValue routine returns the signed and scaled result of a HID control value extracted from a HID report.
old-location: hid\hidp_getscaledusagevalue.htm
old-project: hid
ms.assetid: 0af1a3f2-b933-4232-865c-cccca53fd32e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: HidP_GetScaledUsageValue
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
req.alt-api: HidP_GetScaledUsageValue
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

# HidP_GetScaledUsageValue function



## -description
The <b>HidP_GetScaledUsageValue</b> routine returns the signed and scaled result of a HID control value extracted from a HID report.



## -syntax

````
NTSTATUS __stdcall HidP_GetScaledUsageValue(
  _In_  HIDP_REPORT_TYPE     ReportType,
  _In_  USAGE                UsagePage,
  _In_  USHORT               LinkCollection,
  _In_  USAGE                Usage,
  _Out_ PLONG                UsageValue,
  _In_  PHIDP_PREPARSED_DATA PreparsedData,
  _In_  PCHAR                Report,
  _In_  ULONG                ReportLength
);
````


## -parameters

### -param ReportType [in]

Specifies a <b>HIDP_REPORT_TYPE</b> enumerator value that identifies the type of HID report that contains the <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">HID usage</a> value.


### -param UsagePage [in]

Specifies the usage page of the value to extract.


### -param LinkCollection [in]

Specifies the link collection identifier of the value to extract. A LinkCollection value of zero identifies the top-level collection.


### -param Usage [in]

Specifies the usage of the value to extract.


### -param UsageValue [out]

Pointer to the buffer in which the routine returns the signed and scaled value.


### -param PreparsedData [in]

Pointer to the <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a> of the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> that generated the report located at <i>Report</i>.


### -param Report [in]

Pointer to the report that contains the usage.


### -param ReportLength [in]

Specifies the length, in bytes, of the report located at <i>Report</i>.


## -returns
<b>HidP_GetScaledUsageValue</b> returns one of the following status values:
<dl>
<dt><b>HIDP_STATUS_SUCCESS</b></dt>
</dl>The routine successfully returned the value.
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_TYPE</b></dt>
</dl>The specified report type is not valid.
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_LENGTH</b></dt>
</dl>The specified report length is not valid
<dl>
<dt><b>HIDP_STATUS_BAD_LOG_PHY_VALUES</b></dt>
</dl>The collection returned an illegal logical or physical value. To extract the value returned by the collection, call <a href="hid.hidp_getusagevalue">HidP_GetUsageValue</a>.
<dl>
<dt><b>HIDP_STATUS_NULL</b></dt>
</dl>The current state of the scaled value from the collection is less than the logical minimum or is greater than the logical maximum, and the scaled value has a <b>NULL</b> state.
<dl>
<dt><b>HIDP_STATUS_VALUE_OUT_OF_RANGE</b></dt>
</dl>The current state of the scaled value data from the collection is less than the logical minimum or is greater than the logical maximum.
<dl>
<dt><b>HIDP_STATUS_USAGE_NOT_FOUND</b></dt>
</dl>The specified usage, usage page, or link collection cannot be found in any report supported by the specified top-level collection.
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>The specified value is not contained in the specified report, but is contained in another report supported by the specified top-level collection.

 


## -remarks
The caller-allocated buffers supplied at <i>PreparsedData</i>, <i>UsageValue</i>, and<i> Report </i>must be allocated from nonpaged pool.

User-mode applications and kernel-mode drivers must use <a href="hid.hidp_getusagevaluearray">HidP_GetUsageValueArray</a> to extract data for a <a href="hid.value_capability_arrays#usage_value_array#usage_value_array">usage value array</a>.

If the routine returns status HIDP_STATUS_BAD_LOG_PHY_VALUES, an application or driver can call <a href="hid.hidp_getusagevalue">HidP_GetUsageValue</a> to extract the raw usage data.

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
<a href="hid.hidp_getusagevalue">HidP_GetUsageValue</a>
</dt>
<dt>
<a href="hid.hidp_getusagevaluearray">HidP_GetUsageValueArray</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_GetScaledUsageValue routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

