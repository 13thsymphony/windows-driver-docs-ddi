---
UID: NI.hidclass.IOCTL_HID_GET_COLLECTION_DESCRIPTOR
title: IOCTL_HID_GET_COLLECTION_DESCRIPTOR
author: windows-driver-content
description: The IOCTL_HID_GET_COLLECTION_DESCRIPTOR request obtains a top-level collection's preparsed data, which the HID class driver extracted from the physical device's report descriptor during device initialization.
old-location: hid\ioctl_hid_get_collection_descriptor.htm
ms.assetid: 93684a1a-788d-4b90-b9cc-58a3c4f7b25e
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: ioctl
ms.prod: windows-hardware
ms.technology: hid
req.header: hidclass.h
req.include-header: Hidclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_HID_GET_COLLECTION_DESCRIPTOR
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
ms.keywords: HDAUDIO_STREAM_FORMAT, HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
req.iface: 
---

# IOCTL_HID_GET_COLLECTION_DESCRIPTOR IOCTL



## -description
<p>The IOCTL_HID_GET_COLLECTION_DESCRIPTOR request obtains a top-level collection's <a href="NULL">preparsed data</a>, which the HID class driver extracted from the physical device's report descriptor during device initialization.</p>
<p>For general information about HIDClass devices, see <a href="NULL">HID Collections</a>. </p>


## -syntax

````
typedef struct _HIDP_PREPARSED_DATA * PHIDP_PREPARSED_DATA;

````


## -ioctlparameters

### -input-buffer
<p><b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer specified by <b>Irp-&gt;UserBuffer</b>.</p>

### -input-buffer-length


### -output-buffer
<p><b>Irp-&gt;UserBuffer</b> is a PVOID pointer to a requester-allocated buffer that the HID class driver uses to return a variable length <b>_HIDP_PREPARSED_DATA</b> structure. This buffer must be allocated from nonpaged pool. </p>

<p><b>Irp-&gt;UserBuffer</b> is a PVOID pointer to a requester-allocated buffer that the HID class driver uses to return a variable length <b>_HIDP_PREPARSED_DATA</b> structure. This buffer must be allocated from nonpaged pool. </p>

<p><b>Irp-&gt;UserBuffer</b> is a PVOID pointer to a requester-allocated buffer that the HID class driver uses to return a variable length <b>_HIDP_PREPARSED_DATA</b> structure. This buffer must be allocated from nonpaged pool. </p>

### -output-buffer-length
<p>The size, in bytes, of the preparsed data structure is obtained using <a href="https://msdn.microsoft.com/library/windows/hardware/ff541092">IOCTL_HID_GET_COLLECTION_INFORMATION</a>. </p>

<p>The size, in bytes, of the preparsed data structure is obtained using <a href="https://msdn.microsoft.com/library/windows/hardware/ff541092">IOCTL_HID_GET_COLLECTION_INFORMATION</a>. </p>

<p>The size, in bytes, of the preparsed data structure is obtained using <a href="https://msdn.microsoft.com/library/windows/hardware/ff541092">IOCTL_HID_GET_COLLECTION_INFORMATION</a>. </p>

<p>The size, in bytes, of the preparsed data structure is obtained using <a href="https://msdn.microsoft.com/library/windows/hardware/ff541092">IOCTL_HID_GET_COLLECTION_INFORMATION</a>. </p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to size, in bytes, of the preparesed data.</p>

<p><b>Status</b> is set to STATUS_SUCCESS if the preparsed data was retrieved without error. Otherwise, it is set to an appropriate NTSTATUS error code. If the requester-supplied output buffer is not large enough to hold the preparsed data, then status is set to STATUS_INVALID_BUFFER_SIZE. </p>

<p>The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to size, in bytes, of the preparesed data.</p>

<p><b>Status</b> is set to STATUS_SUCCESS if the preparsed data was retrieved without error. Otherwise, it is set to an appropriate NTSTATUS error code. If the requester-supplied output buffer is not large enough to hold the preparsed data, then status is set to STATUS_INVALID_BUFFER_SIZE. </p>

<p>The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to size, in bytes, of the preparesed data.</p>

<p><b>Status</b> is set to STATUS_SUCCESS if the preparsed data was retrieved without error. Otherwise, it is set to an appropriate NTSTATUS error code. If the requester-supplied output buffer is not large enough to hold the preparsed data, then status is set to STATUS_INVALID_BUFFER_SIZE. </p>

<p>The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to size, in bytes, of the preparesed data.</p>

<p><b>Status</b> is set to STATUS_SUCCESS if the preparsed data was retrieved without error. Otherwise, it is set to an appropriate NTSTATUS error code. If the requester-supplied output buffer is not large enough to hold the preparsed data, then status is set to STATUS_INVALID_BUFFER_SIZE. </p>

<p>The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to size, in bytes, of the preparesed data.</p>

<p><b>Status</b> is set to STATUS_SUCCESS if the preparsed data was retrieved without error. Otherwise, it is set to an appropriate NTSTATUS error code. If the requester-supplied output buffer is not large enough to hold the preparsed data, then status is set to STATUS_INVALID_BUFFER_SIZE. </p>

## -remarks
<p>The <b>_HIDP_PREPARSED_DATA</b> structure contains a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="NULL">preparsed data</a>.</p>

<p>A user-mode application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff539679">HidD_GetPreparsedData</a> to obtain a top-level collection's preparsed data in a variable length _HIDP_PREPARSED_DATA structure.</p>

<p>A kernel-mode driver uses an <b>IOCTL_HID_GET_COLLECTION_DESCRIPTOR</b> request to obtain a pointer to a top-level collection's preparsed data.</p>

<p>The internal structure of a _HIDP_PREPARSED_DATA structure is reserved for internal system use.</p>

<p>The <b>_HIDP_PREPARSED_DATA</b> structure contains a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="NULL">preparsed data</a>.</p>

<p>A user-mode application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff539679">HidD_GetPreparsedData</a> to obtain a top-level collection's preparsed data in a variable length _HIDP_PREPARSED_DATA structure.</p>

<p>A kernel-mode driver uses an <b>IOCTL_HID_GET_COLLECTION_DESCRIPTOR</b> request to obtain a pointer to a top-level collection's preparsed data.</p>

<p>The internal structure of a _HIDP_PREPARSED_DATA structure is reserved for internal system use.</p>

<p>The <b>_HIDP_PREPARSED_DATA</b> structure contains a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="NULL">preparsed data</a>.</p>

<p>A user-mode application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff539679">HidD_GetPreparsedData</a> to obtain a top-level collection's preparsed data in a variable length _HIDP_PREPARSED_DATA structure.</p>

<p>A kernel-mode driver uses an <b>IOCTL_HID_GET_COLLECTION_DESCRIPTOR</b> request to obtain a pointer to a top-level collection's preparsed data.</p>

<p>The internal structure of a _HIDP_PREPARSED_DATA structure is reserved for internal system use.</p>

<p>The <b>_HIDP_PREPARSED_DATA</b> structure contains a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="NULL">preparsed data</a>.</p>

<p>A user-mode application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff539679">HidD_GetPreparsedData</a> to obtain a top-level collection's preparsed data in a variable length _HIDP_PREPARSED_DATA structure.</p>

<p>A kernel-mode driver uses an <b>IOCTL_HID_GET_COLLECTION_DESCRIPTOR</b> request to obtain a pointer to a top-level collection's preparsed data.</p>

<p>The internal structure of a _HIDP_PREPARSED_DATA structure is reserved for internal system use.</p>

<p>The <b>_HIDP_PREPARSED_DATA</b> structure contains a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="NULL">preparsed data</a>.</p>

<p>A user-mode application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff539679">HidD_GetPreparsedData</a> to obtain a top-level collection's preparsed data in a variable length _HIDP_PREPARSED_DATA structure.</p>

<p>A kernel-mode driver uses an <b>IOCTL_HID_GET_COLLECTION_DESCRIPTOR</b> request to obtain a pointer to a top-level collection's preparsed data.</p>

<p>The internal structure of a _HIDP_PREPARSED_DATA structure is reserved for internal system use.</p>

<p>The <b>_HIDP_PREPARSED_DATA</b> structure contains a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="NULL">preparsed data</a>.</p>

<p>A user-mode application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff539679">HidD_GetPreparsedData</a> to obtain a top-level collection's preparsed data in a variable length _HIDP_PREPARSED_DATA structure.</p>

<p>A kernel-mode driver uses an <b>IOCTL_HID_GET_COLLECTION_DESCRIPTOR</b> request to obtain a pointer to a top-level collection's preparsed data.</p>

<p>The internal structure of a _HIDP_PREPARSED_DATA structure is reserved for internal system use.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538893">HidD_FreePreparsedData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539679">HidD_GetPreparsedData</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_GET_COLLECTION_DESCRIPTOR control code%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
