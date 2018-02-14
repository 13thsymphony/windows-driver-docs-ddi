---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_ENABLE_PORT
title: IOCTL_INTERNAL_USB_ENABLE_PORT
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_ENABLE_PORT IOCTL has been deprecated. Do not use.
old-location: buses\ioctl_internal_usb_enable_port.htm
old-project: usbref
ms.assetid: 6f15a559-fb6b-47d5-a101-43464ed80d0f
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.ioctl_internal_usb_enable_port, IOCTL_INTERNAL_USB_ENABLE_PORT control code [Buses], IOCTL_INTERNAL_USB_ENABLE_PORT, usbioctl/IOCTL_INTERNAL_USB_ENABLE_PORT, usbirp_eee71b69-fc0a-446a-807b-6f776e634c9d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Microsoft Windows 2000, Windows XP and Windows Server 2003. It is not supported in Windows Vista and later operating systems.
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
-	usbioctl.h
apiname:
-	IOCTL_INTERNAL_USB_ENABLE_PORT
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_ENABLE_PORT IOCTL
The <b>IOCTL_INTERNAL_USB_ENABLE_PORT</b> IOCTL has been deprecated. Do not use.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<text></text>

### Input Buffer Length
<text></text>

### Output Buffer
<text></text>

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [XREF-LINK:NTSTATUS Values].


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Microsoft Windows 2000, Windows XP and Windows Server 2003. It is not supported in Windows Vista and later operating systems. Supported in Microsoft Windows 2000, Windows XP and Windows Server 2003. It is not supported in Windows Vista and later operating systems. |
| **Header** | usbioctl.h (include Usbioctl.h) |