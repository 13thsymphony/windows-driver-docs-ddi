---
UID: NI:hidport.IOCTL_HID_GET_DEVICE_ATTRIBUTES
title: IOCTL_HID_GET_DEVICE_ATTRIBUTES
author: windows-driver-content
description: The IOCTL_HID_GET_DEVICE_ATTRIBUTES request obtains a HIDClass device's attributes in a HID_DEVICE_ATTRIBUTES structure.
old-location: hid\ioctl_hid_get_device_attributes.htm
old-project: hid
ms.assetid: ee68c045-e99a-471d-ae22-396673d68168
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hid.ioctl_hid_get_device_attributes, IOCTL_HID_GET_DEVICE_ATTRIBUTES control code [Human Input Devices], IOCTL_HID_GET_DEVICE_ATTRIBUTES, hidport/IOCTL_HID_GET_DEVICE_ATTRIBUTES, hidioreq_417c2e10-9ca8-4a9f-8a30-1ff401b65b13.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hidport.h
apiname:
-	IOCTL_HID_GET_DEVICE_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: USAGE_AND_PAGE, *PUSAGE_AND_PAGE
---

# IOCTL_HID_GET_DEVICE_ATTRIBUTES IOCTL
The IOCTL_HID_GET_DEVICE_ATTRIBUTES request obtains a HIDClass device's attributes in a <a href="..\hidport\ns-hidport-_hid_device_attributes.md">HID_DEVICE_ATTRIBUTES</a> structure.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>Parameters.DeviceIoControl.OutputBufferLength</b> contains the length, in bytes, of the HID class driver's buffer located at <b>Irp-&gt;UserBuffer</b>.

### Input Buffer Length
The size, in bytes, of the buffer must be greater than or equal to the size, in bytes, of a HID_DEVICE_ATTRIBUTES structure.

### Output Buffer
The HID minidriver returns the device attributes in a HID_DEVICE_ATTRIBUTES structure at <b>Irp-&gt;UserBuffer</b>.

### Output Buffer Length
The size of a HID_DEVICE_ATTRIBUTES structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The HID minidriver sets the following fields of <b>Irp-&gt;IoStatus</b>:
<ul>
<li>
<b>Information</b> is set to the number of bytes transferred from the device.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hidport.h (include Hidport.h) |

## See Also

<a href="..\hidport\ni-hidport-ioctl_hid_get_device_descriptor.md">IOCTL_HID_GET_DEVICE_DESCRIPTOR</a>

<a href="..\hidport\ns-hidport-_hid_device_attributes.md">HID_DEVICE_ATTRIBUTES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_GET_DEVICE_ATTRIBUTES control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>