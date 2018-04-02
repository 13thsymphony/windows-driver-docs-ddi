---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE
title: IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE I/O request unregisters the driver of a USB multi-function device (composite driver) and releases all resources that are associated with registration.
old-location: buses\ioctl_internal_usb_unregister_composite_driver.htm
old-project: usbref
ms.assetid: B9DD8FDB-CD78-41BD-BE43-A0F61695B3EB
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE, IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE control code [Buses], buses.ioctl_internal_usb_unregister_composite_driver, usbioctl/IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbioctl.h
api_name:
-	IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE IOCTL
The <b>IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE</b> 
   I/O request unregisters the  driver of a USB multi-function device (composite driver) and releases all resources that are associated with registration. The request is successful only if the composite driver was previously registered with the underlying USB driver stack through the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450854">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a> request.



<b>IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE</b> is a kernel-mode I/O control request. This request targets the Universal Serial Bus (USB) hub physical device object (PDO). This request must be sent at an interrupt request level (IRQL) of PASSIVE_LEVEL.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The USB driver stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.

## Remarks
You must send the <b>IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE</b> request in the composite driver's  remove-device (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>) routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | usbioctl.h (include Usbioctl.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450897">How to Register a Composite Device</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450854">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a>