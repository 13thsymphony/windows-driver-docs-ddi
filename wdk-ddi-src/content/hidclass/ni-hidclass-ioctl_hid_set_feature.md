---
UID: NI:hidclass.IOCTL_HID_SET_FEATURE
title: IOCTL_HID_SET_FEATURE
author: windows-driver-content
description: IOCTL_HID_SET_FEATURE sends a feature report to a HIDClass device.
old-location: hid\ioctl_hid_set_feature.htm
old-project: hid
ms.assetid: 20471ee0-33c3-4ffa-bce8-b008569cb268
ms.author: windowsdriverdev
ms.date: 12/21/2017
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
req.alt-api: IOCTL_HID_SET_FEATURE
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
req.typenames: HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
---

# IOCTL_HID_SET_FEATURE IOCTL



## -description
IOCTL_HID_SET_FEATURE sends a feature report to a HIDClass device.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -ioctlparameters

### -input-buffer
<b>Irp-&gt;UserBuffer</b> points to a <a href="..\hidclass\ns-hidclass-_hid_xfer_packet.md">HID_XFER_PACKET</a> structure that the HID class driver uses to input the following members:



Pointer to a requester-allocated input buffer that contains a feature report.

Specifies the size, in bytes, of the input buffer.

Specifies the report ID for a top-level collection .


### -input-buffer-length
 The size of a <a href="..\hidclass\ns-hidclass-_hid_xfer_packet.md">HID_XFER_PACKET</a> structure.


### -output-buffer

       None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block

       HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp-&gt;IoStatus</b>:

<b>Information</b> is set to the number of bytes transferred to the device.

<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

HID minidrivers that call other drivers with this IOCTL to carry out the I/O, should ensure that the <b>Information</b> field of the status block is correct and not change the contents of the <b>Status</b> field.


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
<a href="..\hidsdi\nf-hidsdi-hidd_getfeature.md">HidD_GetFeature</a>
</dt>
<dt>
<a href="..\hidsdi\nf-hidsdi-hidd_getinputreport.md">HidD_GetInputReport</a>
</dt>
<dt>
<a href="..\hidsdi\nf-hidsdi-hidd_setfeature.md">HidD_SetFeature</a>
</dt>
<dt>
<a href="..\hidsdi\nf-hidsdi-hidd_setoutputreport.md">HidD_SetOutputReport</a>
</dt>
<dt>
<a href="..\hidclass\ns-hidclass-_hid_xfer_packet.md">HID_XFER_PACKET</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_feature.md">IOCTL_HID_GET_FEATURE</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_input_report.md">IOCTL_HID_GET_INPUT_REPORT</a>
</dt>
<dt>
<a href="..\hidport\ni-hidport-ioctl_hid_read_report.md">IOCTL_HID_READ_REPORT</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_set_output_report.md">IOCTL_HID_SET_OUTPUT_REPORT</a>
</dt>
<dt>
<a href="..\hidport\ni-hidport-ioctl_hid_write_report.md">IOCTL_HID_WRITE_REPORT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_SET_FEATURE control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

