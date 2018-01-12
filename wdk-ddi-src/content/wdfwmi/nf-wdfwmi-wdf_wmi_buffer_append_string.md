---
UID: NF:wdfwmi.WDF_WMI_BUFFER_APPEND_STRING
title: WDF_WMI_BUFFER_APPEND_STRING function
author: windows-driver-content
description: The WDF_WMI_BUFFER_APPEND_STRING function copies a specified Unicode string into a specified buffer in the format that WMI requires.
old-location: wdf\wdf_wmi_buffer_append_string.htm
old-project: wdf
ms.assetid: 23d65788-23ce-4ed7-8b68-890c1c3a4100
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WDF_WMI_BUFFER_APPEND_STRING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WDF_WMI_BUFFER_APPEND_STRING
req.alt-loc: None,None.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: None
req.dll: 
req.irql: 
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# WDF_WMI_BUFFER_APPEND_STRING function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_WMI_BUFFER_APPEND_STRING</b> function copies a specified Unicode string into a specified buffer in the format that WMI requires.



## -syntax

````
NTSTATUS WDF_WMI_BUFFER_APPEND_STRING(
  _Out_ PVOID            Buffer,
  _In_  ULONG            BufferLength,
  _In_  PCUNICODE_STRING String,
  _Out_ PULONG           RequiredSize
);
````


## -parameters

### -param Buffer [out]

A pointer to a destination buffer that receives the string.


### -param BufferLength [in]

The length, in bytes, of the destination buffer that receives the string.


### -param String [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the string to be copied.


### -param RequiredSize [out]

A pointer to a location that receives the number of bytes that are required to store the specified string in the destination buffer.


## -returns
<b>WDF_WMI_BUFFER_APPEND_STRING</b> returns STATUS_SUCCESS if the operation succeeds. If the destination buffer is too small to hold the Unicode string that the <i>String</i> parameter specifies, the function returns STATUS_BUFFER_TOO_SMALL.


## -remarks
WMI requires that strings that an <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_query_instance.md">EvtWmiInstanceQueryInstance</a> callback function returns be preceded by a byte count. The <b>WDF_WMI_BUFFER_APPEND_STRING</b> function calculates the byte count, stores it in the destination buffer, and then copies the string from the <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure into the destination buffer. 

When <b>WDF_WMI_BUFFER_APPEND_STRING</b> returns, the location that the <i>RequiredSize</i> parameter points to contains the total number of bytes that were written to the buffer. To find the first buffer address that follows the string, your driver can pass the <i>RequiredSize</i> value to the WDF_PTR_ADD_OFFSET macro that is defined in <i>Wdfcore.h</i>.

The following code example is from the <a href="wdf.sample_kmdf_drivers">Serial</a> sample driver. This example is an <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_query_instance.md">EvtWmiInstanceQueryInstance</a> callback function that obtains a device's symbolic name and copies the name into the callback function's output buffer.


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
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfwmi.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>None</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_query_instance.md">EvtWmiInstanceQueryInstance</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_WMI_BUFFER_APPEND_STRING function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

