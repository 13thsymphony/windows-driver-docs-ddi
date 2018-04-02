---
UID: NI:usbprint.IOCTL_USBPRINT_VENDOR_SET_COMMAND
title: IOCTL_USBPRINT_VENDOR_SET_COMMAND
author: windows-driver-content
description: The IOCTL_USBPRINT_VENDOR_SET_COMMAND request allows upper-layer software (such as a language monitor) to issue a vendor-specific SET command to the target device.
old-location: print\ioctl_usbprint_vendor_set_command.htm
old-project: print
ms.assetid: 3fbb3e5d-e7a3-4d76-9996-50375ed9fd03
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_USBPRINT_VENDOR_SET_COMMAND, IOCTL_USBPRINT_VENDOR_SET_COMMAND control code [Print Devices], print.ioctl_usbprint_vendor_set_command, usbioctl_b3ea3ada-47c2-4acc-b08c-2d16e9d3ead1.xml, usbprint/IOCTL_USBPRINT_VENDOR_SET_COMMAND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbprint.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbprint.h
api_name:
-	IOCTL_USBPRINT_VENDOR_SET_COMMAND
product: Windows
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION
req.product: Windows 10 or later.
---

# IOCTL_USBPRINT_VENDOR_SET_COMMAND IOCTL
The <b>IOCTL_USBPRINT_VENDOR_SET_COMMAND</b> request allows upper-layer software (such as a language monitor) to issue a vendor-specific SET command to the target device.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A pointer to a input buffer, an array of UCHAR elements. The meaning of each array element is shown in the following table.

<table>
<tr>
<th>Array Element</th>
<th>Contents</th>
</tr>
<tr>
<td>
<i>lpInBuffer</i>[0]

</td>
<td>
Vendor request code

</td>
</tr>
<tr>
<td>
<i>lpInBuffer</i>[1]

</td>
<td>
Vendor request value (most significant byte)

</td>
</tr>
<tr>
<td>
<i>lpInBuffer</i>[2]

</td>
<td>
Vendor request value (least significant byte)

</td>
</tr>
<tr>
<td>
<i>lpInBuffer</i>[3], ...

</td>
<td>
Any additional data to be sent as part of the command

</td>
</tr>
</table>

### Input Buffer Length
The size of the input buffer, in bytes.

### Output Buffer
Not used in this operation; set this parameter to <b>NULL</b>.

### Output Buffer Length
Not used in this operation; set this parameter to 0.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbprint.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551815">IOCTL_USBPRINT_VENDOR_GET_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>