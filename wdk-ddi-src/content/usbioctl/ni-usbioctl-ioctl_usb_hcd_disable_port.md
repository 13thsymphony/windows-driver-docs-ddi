---
UID: NI:usbioctl.IOCTL_USB_HCD_DISABLE_PORT
title: IOCTL_USB_HCD_DISABLE_PORT
author: windows-driver-content
description: The IOCTL_USB_HCD_DISABLE_PORT IOCTL has been deprecated. Do not use.
old-location: buses\ioctl_usb_hcd_disable_port.htm
old-project: usbref
ms.assetid: c0ae41be-1b37-4410-8e7a-611a66c599c1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_USB_HCD_DISABLE_PORT, IOCTL_USB_HCD_DISABLE_PORT control code [Buses], buses.ioctl_usb_hcd_disable_port, usbioctl/IOCTL_USB_HCD_DISABLE_PORT, usbirp_558a0a61-e35f-4015-9f72-df33e85c8c59.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows Server 2003, Windows XP, and Windows 2000, but it is not available on Windows Vista.
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
-	Usbioctl.h
api_name:
-	IOCTL_USB_HCD_DISABLE_PORT
product:
- Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_HCD_DISABLE_PORT IOCTL
The <b>IOCTL_USB_HCD_DISABLE_PORT</b> IOCTL has been deprecated. Do not use.

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

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Microsoft Windows Server 2003, Windows XP, and Windows 2000, but it is not available on Windows Vista. Available on Microsoft Windows Server 2003, Windows XP, and Windows 2000, but it is not available on Windows Vista. |
| **Header** | usbioctl.h (include Usbioctl.h) |