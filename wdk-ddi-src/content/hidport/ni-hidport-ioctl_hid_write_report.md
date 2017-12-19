---
UID: NI.hidport.IOCTL_HID_WRITE_REPORT
title: IOCTL_HID_WRITE_REPORT
author: windows-driver-content
description: The IOCTL_HID_WRITE_REPORT request sends a HID report to a HIDClass device.
old-location: hid\ioctl_hid_write_report.htm
old-project: hid
ms.assetid: 30b56c97-f135-4603-a5f0-3ed2105aae59
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: HidRegisterMinidriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidport.h
req.include-header: Hidport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_HID_WRITE_REPORT
req.alt-loc: hidport.h
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

# IOCTL_HID_WRITE_REPORT IOCTL



## -description
The IOCTL_HID_WRITE_REPORT request sends a HID report to a HIDClass device.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -ioctlparameters

### -input-buffer
<b>Irp-&gt;UserBuffer </b> points to a <a href="hid.hid_xfer_packet">HID_XFER_PACKET</a> structure the contains the parameters and report to be transmitted to the device. The following members are used:



A pointer to a resident buffer containing the data to be sent to the device.

Specifies the length of the buffer provided at <b>reportBuffer</b>.

Specifies the report identifier, for this collection, of the report data to be written to the device.


### -input-buffer-length
The size of a <a href="hid.hid_xfer_packet">HID_XFER_PACKET</a> structure.


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

HID minidrivers that call other drivers with this IOCTL to carry out the I/O to their device, should ensure that the <b>Information</b> field of the status block is correct and not change the contents of the <b>Status</b> field.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hidport.h (include Hidport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="hid.hidd_getfeature">HidD_GetFeature</a>
</dt>
<dt>
<a href="hid.hidd_getinputreport">HidD_GetInputReport</a>
</dt>
<dt>
<a href="hid.hidd_setfeature">HidD_SetFeature</a>
</dt>
<dt>
<a href="hid.hidd_setoutputreport">HidD_SetOutputReport</a>
</dt>
<dt>
<a href="hid.hid_xfer_packet">HID_XFER_PACKET</a>
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
<a href="..\hidclass\ni-hidclass-ioctl_hid_set_feature.md">IOCTL_HID_SET_FEATURE</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_set_output_report.md">IOCTL_HID_SET_OUTPUT_REPORT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_WRITE_REPORT control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

