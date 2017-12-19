---
UID: NI.hidclass.IOCTL_HID_SET_S0_IDLE_TIMEOUT
title: IOCTL_HID_SET_S0_IDLE_TIMEOUT
author: windows-driver-content
description: The IOCTL_HID_SET_S0_IDLE_TIMEOUT request is used by a client to inform the HID class driver about the client's preferred idle timeout value.
old-location: hid\ioctl_hid_set_s0_idle_timeout.htm
old-project: hid
ms.assetid: 9372E6D5-0E0B-4916-929D-73532FB6A5D6
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
req.alt-api: IOCTL_HID_SET_S0_IDLE_TIMEOUT
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

# IOCTL_HID_SET_S0_IDLE_TIMEOUT IOCTL



## -description
The <b>IOCTL_HID_SET_S0_IDLE_TIMEOUT</b> 
   request is used by a client to inform the HID class driver about the client's preferred idle timeout value.

When the client sets this value to zero (0), it informs the HID class driver that the preferred idle timeout value is no longer valid. In this case, the HID class driver will start to use the default idle timeout value.



## -ioctlparameters

### -input-buffer

       The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member specifies the size, in bytes, of a requester-allocated output buffer. 


### -input-buffer-length
This is a buffer of size ULONG.


### -output-buffer
The <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> member is a pointer to the requestor-allocated buffer that the client uses to return the idle timeout value.


### -output-buffer-length



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