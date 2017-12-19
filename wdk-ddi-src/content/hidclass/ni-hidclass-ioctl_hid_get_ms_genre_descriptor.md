---
UID: NI.hidclass.IOCTL_HID_GET_MS_GENRE_DESCRIPTOR
title: IOCTL_HID_GET_MS_GENRE_DESCRIPTOR
author: windows-driver-content
description: The IOCTL_HID_GET_MS_GENRE_DESCRIPTOR request is used for retrieving the genre descriptor for the device.
old-location: hid\ioctl_hid_get_ms_genre_descriptor.htm
old-project: hid
ms.assetid: C83C6086-369D-41DB-BEB5-33B3A0C1C0AE
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
req.alt-api: IOCTL_HID_GET_MS_GENRE_DESCRIPTOR
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

# IOCTL_HID_GET_MS_GENRE_DESCRIPTOR IOCTL



## -description
The <b>IOCTL_HID_GET_MS_GENRE_DESCRIPTOR</b> 
   request is used for retrieving the genre descriptor for the device.



## -ioctlparameters

### -input-buffer

       The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member specifies the size, in bytes, of a requester-allocated output buffer. 


### -input-buffer-length



### -output-buffer
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a <a href="kernel.ntstatus_value">NTSTATUS</a> code.


### -output-buffer-length
The size of a status code.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a <a href="kernel.ntstatus_value">NTSTATUS</a> code.


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