---
UID: NI:usbioctl.IOCTL_USB_DIAGNOSTIC_MODE_ON
title: IOCTL_USB_DIAGNOSTIC_MODE_ON
author: windows-driver-content
description: The IOCTL_USB_DIAGNOSTIC_MODE_ON I/O control has been deprecated. Do not use.
old-location: buses\ioctl_usb_diagnostic_mode_on.htm
old-project: usbref
ms.assetid: 9b3b7d11-a91c-4905-b639-d9843f05d65e
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.ioctl_usb_diagnostic_mode_on, IOCTL_USB_DIAGNOSTIC_MODE_ON control code [Buses], IOCTL_USB_DIAGNOSTIC_MODE_ON, usbioctl/IOCTL_USB_DIAGNOSTIC_MODE_ON, usbirp_c1493559-ce0a-4b79-8c7b-5fff2f3c83b3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
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
-	Usbioctl.h
apiname:
-	IOCTL_USB_DIAGNOSTIC_MODE_ON
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_DIAGNOSTIC_MODE_ON IOCTL
The <b>IOCTL_USB_DIAGNOSTIC_MODE_ON</b> I/O control has been deprecated. Do not use.

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
| **Header** | usbioctl.h (include Usbioctl.h) |