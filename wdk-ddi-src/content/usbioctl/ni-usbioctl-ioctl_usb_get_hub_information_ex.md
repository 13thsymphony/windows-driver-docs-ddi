---
UID: NI:usbioctl.IOCTL_USB_GET_HUB_INFORMATION_EX
title: IOCTL_USB_GET_HUB_INFORMATION_EX
author: windows-driver-content
description: The IOCTL_USB_GET_HUB_INFORMATION_EX I/O control request is sent by an application to retrieve information about a USB hub in a USB_HUB_INFORMATION_EX structure.The request retrieves the highest port number on the hub.
old-location: buses\ioctl_usb_get_hub_information_ex.htm
old-project: usbref
ms.assetid: 518AB292-A1E7-48CE-B967-C6559580E326
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_USB_GET_HUB_INFORMATION_EX, IOCTL_USB_GET_HUB_INFORMATION_EX control code [Buses], buses.ioctl_usb_get_hub_information_ex, usbioctl/IOCTL_USB_GET_HUB_INFORMATION_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: None supported
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
-	Usbioctl.h
api_name:
-	IOCTL_USB_GET_HUB_INFORMATION_EX
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_HUB_INFORMATION_EX IOCTL
The <b>IOCTL_USB_GET_HUB_INFORMATION_EX</b> I/O control request is sent by an application to retrieve information about a USB hub in a <a href="..\usbioctl\ns-usbioctl-_usb_hub_information_ex.md">USB_HUB_INFORMATION_EX</a> structure.

The request retrieves the highest port number on the hub. For USB 2.0 and SuperSpeed hubs (non-root hubs), the request also retrieves the associated hub descriptors, as defined in USB 2.0 and 3.0 Specifications, respectively. 

<b>IOCTL_USB_GET_HUB_INFORMATION_EX</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>AssociatedIrp.SystemBuffer</b> points to a caller-allocated    <a href="..\usbioctl\ns-usbioctl-_usb_hub_information_ex.md">USB_HUB_INFORMATION_EX</a> structure.

### Input Buffer Length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member indicates the size, in bytes, of the caller-allocated buffer whose size equals <code>sizeof(USB_HUB_INFORMATION_EX)</code>.

### Output Buffer
On output, the <a href="..\usbioctl\ns-usbioctl-_usb_hub_information_ex.md">USB_HUB_INFORMATION_EX</a> structure that is pointed to by  <b>AssociatedIrp.SystemBuffer</b> is filled with information about the hub.

### Output Buffer Length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the output buffer <b>SystemBuffer</b>.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB driver stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="..\usbioctl\ns-usbioctl-_usb_hub_information_ex.md">USB_HUB_INFORMATION_EX</a>