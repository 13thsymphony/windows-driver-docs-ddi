---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND
title: IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND IOCTL is used by the USB hub driver. Do not use.
old-location: buses\ioctl_internal_usb_req_global_suspend.htm
old-project: usbref
ms.assetid: e724ae02-642d-464c-b1d2-e43a657b4e9c
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.ioctl_internal_usb_req_global_suspend, IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND control code [Buses], IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND, usbioctl/IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND IOCTL
The <b>IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND</b> IOCTL is used by the USB hub driver. Do not use.

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
| **Header** | usbioctl.h |