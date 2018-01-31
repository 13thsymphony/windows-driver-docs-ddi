---
UID : NI:hidport.IOCTL_HID_WRITE_REPORT
title : IOCTL_HID_WRITE_REPORT
author : windows-driver-content
description : The IOCTL_HID_WRITE_REPORT request sends a HID report to a HIDClass device.
old-location : hid\ioctl_hid_write_report.htm
old-project : hid
ms.assetid : 30b56c97-f135-4603-a5f0-3ed2105aae59
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : hid.ioctl_hid_write_report, IOCTL_HID_WRITE_REPORT control code [Human Input Devices], IOCTL_HID_WRITE_REPORT, hidport/IOCTL_HID_WRITE_REPORT, hidioreq_0b1eb214-55b0-4659-bdf7-866cf03a7be6.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : hidport.h
req.include-header : Hidport.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUSAGE_AND_PAGE, USAGE_AND_PAGE"
---

# IOCTL_HID_WRITE_REPORT IOCTL
The IOCTL_HID_WRITE_REPORT request sends a HID report to a HIDClass device.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>Irp-&gt;UserBuffer </b> points to a <a href="..\hidclass\ns-hidclass-_hid_xfer_packet.md">HID_XFER_PACKET</a> structure the contains the parameters and report to be transmitted to the device. The following members are used:

### Input Buffer Length
The size of a <a href="..\hidclass\ns-hidclass-_hid_xfer_packet.md">HID_XFER_PACKET</a> structure.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp-&gt;IoStatus</b>:
<ul>
<li>
<b>Information</b> is set to the number of bytes transferred to the device.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>HID minidrivers that call other drivers with this IOCTL to carry out the I/O to their device, should ensure that the <b>Information</b> field of the status block is correct and not change the contents of the <b>Status</b> field.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | hidport.h (include Hidport.h) |
| **IRQL** |  |

## See Also

<a href="..\hidsdi\nf-hidsdi-hidd_setoutputreport.md">HidD_SetOutputReport</a>

<a href="..\hidport\ni-hidport-ioctl_hid_read_report.md">IOCTL_HID_READ_REPORT</a>

<a href="..\hidsdi\nf-hidsdi-hidd_setfeature.md">HidD_SetFeature</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_get_feature.md">IOCTL_HID_GET_FEATURE</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_set_output_report.md">IOCTL_HID_SET_OUTPUT_REPORT</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_set_feature.md">IOCTL_HID_SET_FEATURE</a>

<a href="..\hidsdi\nf-hidsdi-hidd_getinputreport.md">HidD_GetInputReport</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_get_input_report.md">IOCTL_HID_GET_INPUT_REPORT</a>

<a href="..\hidsdi\nf-hidsdi-hidd_getfeature.md">HidD_GetFeature</a>

<a href="..\hidclass\ns-hidclass-_hid_xfer_packet.md">HID_XFER_PACKET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_WRITE_REPORT control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>