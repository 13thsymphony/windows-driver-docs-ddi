---
UID: NI:hidport.IOCTL_HID_DEACTIVATE_DEVICE
title: IOCTL_HID_DEACTIVATE_DEVICE
author: windows-driver-content
description: The IOCTL_HID_DEACTIVATE_DEVICE request deactivates a HIDClass device, which causes it to stop operations and terminate all outstanding I/O requests.
old-location: hid\ioctl_hid_deactivate_device.htm
old-project: hid
ms.assetid: 87af450c-0f62-481d-8c7d-24c77f221fc5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_HID_DEACTIVATE_DEVICE, IOCTL_HID_DEACTIVATE_DEVICE control code [Human Input Devices], hid.ioctl_hid_deactivate_device, hidioreq_35c75bec-696b-4043-bdb4-2425ff0ad6db.xml, hidport/IOCTL_HID_DEACTIVATE_DEVICE
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
-	hidport.h
api_name:
-	IOCTL_HID_DEACTIVATE_DEVICE
product:
- Windows
targetos: Windows
req.typenames: USAGE_AND_PAGE, *PUSAGE_AND_PAGE
---

# IOCTL_HID_DEACTIVATE_DEVICE IOCTL
The IOCTL_HID_DEACTIVATE_DEVICE request deactivates a HIDClass device, which causes it to stop operations and terminate all outstanding I/O requests.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>Parameters.DeviceIoControl.Type3InputBuffer</b> contains the collection identifier, as a ULONG value, of the collection that is ceasing operations.

### Input Buffer Length
The length of a ULONG value.

### Output Buffer
None.

### Output Buffer Length
None

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to zero.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>
HID minidrivers that call other drivers with this IRP to carry out the I/O to their device should ensure that the <b>Information</b> field of the status block is zero and must not change the contents of the <b>Status</b> field.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hidport.h (include Hidport.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439611">IOCTL_HID_ACTIVATE_DEVICE</a>