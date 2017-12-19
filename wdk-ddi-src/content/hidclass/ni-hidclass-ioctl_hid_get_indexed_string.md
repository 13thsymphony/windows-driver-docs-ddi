---
UID: NI.hidclass.IOCTL_HID_GET_INDEXED_STRING
title: IOCTL_HID_GET_INDEXED_STRING
author: windows-driver-content
description: The IOCTL_HID_GET_INDEXED_STRING request obtains a specified embedded string for a top-level collection.
old-location: hid\ioctl_hid_get_indexed_string.htm
old-project: hid
ms.assetid: 6139be09-0206-4249-a581-077063339817
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT, PHDAUDIO_STREAM_FORMAT, HDAUDIO_STREAM_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidclass.h
req.include-header: Hidclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_HID_GET_INDEXED_STRING
req.alt-loc: hidclass.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# IOCTL_HID_GET_INDEXED_STRING IOCTL



## -description
The IOCTL_HID_GET_INDEXED_STRING request obtains a specified embedded string for a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>. The retrieved string is a NULL-terminated wide character string in a human-readable format.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -ioctlparameters

### -input-buffer
IOCTL_HID_GET_INDEXED_STRING uses two input buffers.

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer at the location pointed to by <b>Irp-&gt;MdlAddress</b>. If the output buffer is not large enough to hold the entire NULL-terminated embedded string, the request returns nothing in the output buffer. The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

<b>Parameters.DeviceIoControl.Type3InputBuffer</b> contains an INT value that describes the string to be retrieved. The most significant two bytes of the INT value contain the language ID (for example, a value of 1033 indicates English). The least significant two bytes of the INT value contain the string index. 


### -input-buffer-length
For <b>Parameters.DeviceIoControl.OutputBufferLength</b>, the maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

For <b>Parameters.DeviceIoControl.Type3InputBuffer</b>, the size of an INT value.


### -output-buffer
<b>Irp-&gt;MdlAddress</b> points to a buffer to receive the retrieved string (a NULL-terminated wide character string). Note that unlike most device control IRPs for HID minidrivers, this IRP does not use METHOD_NEITHER buffering. In particular, it must be distinguished from IOCTL_HID_GET_STRING whose output buffer is identified by <b>Irp-&gt;UserBuffer</b>.


### -output-buffer-length
The size of the retrieved string (a NULL-terminated wide character string).


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:

<b>Information</b> is set to the number of bytes transferred from the device.

<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hidclass.h (include Hidclass.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="hid.hidd_getindexedstring">HidD_GetIndexedString</a>
</dt>
<dt>
<a href="hid.hidd_getmanufacturerstring">HidD_GetManufacturerString</a>
</dt>
<dt>
<a href="hid.hidd_getproductstring">HidD_GetProductString</a>
</dt>
<dt>
<a href="hid.hidd_getserialnumberstring">HidD_GetSerialNumberString</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_indexed_string.md">IOCTL_HID_GET_INDEXED_STRING</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_manufacturer_string.md">IOCTL_HID_GET_MANUFACTURER_STRING</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_product_string.md">IOCTL_HID_GET_PRODUCT_STRING</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_serialnumber_string.md">IOCTL_HID_GET_SERIALNUMBER_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_GET_INDEXED_STRING control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

