---
UID: NI.hidclass.IOCTL_GET_PHYSICAL_DESCRIPTOR
title: IOCTL_GET_PHYSICAL_DESCRIPTOR
author: windows-driver-content
description: The IOCTL_GET_PHYSICAL_DESCRIPTOR request obtains the physical descriptor of a top-level collection.
old-location: hid\ioctl_get_physical_descriptor.htm
old-project: hid
ms.assetid: cf15dd7f-4568-40c7-b2e4-7cec8239df0b
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _HDAUDIO_STREAM_FORMAT, HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
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
req.alt-api: IOCTL_GET_PHYSICAL_DESCRIPTOR
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

# IOCTL_GET_PHYSICAL_DESCRIPTOR IOCTL



## -description
The IOCTL_GET_PHYSICAL_DESCRIPTOR request obtains the physical descriptor of a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.
For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters

### -input-buffer
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer. 

### -input-buffer-length


### -output-buffer
<b>Irp-&gt;MdlAddress</b> must point to the buffer that will receive the physical descriptor. 

### -output-buffer-length


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The HID class driver sets the <b>Status</b> member of <b>Irp-&gt;IoStatus</b> to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

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
<a href="hid.hidd_getphysicaldescriptor">HidD_GetPhysicalDescriptor</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_GET_PHYSICAL_DESCRIPTOR control code%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
