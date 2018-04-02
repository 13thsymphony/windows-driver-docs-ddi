---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_BUSGUID_INFO
title: IOCTL_INTERNAL_USB_GET_BUSGUID_INFO
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_GET_BUSGUID_INFO IOCTL has been deprecated. Do not use.
old-location: buses\ioctl_internal_usb_get_busguid_info.htm
old-project: usbref
ms.assetid: 79a09c8d-ddea-4335-ac90-11438f4bede6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_INTERNAL_USB_GET_BUSGUID_INFO, IOCTL_INTERNAL_USB_GET_BUSGUID_INFO control code [Buses], buses.ioctl_internal_usb_get_busguid_info, usbioctl/IOCTL_INTERNAL_USB_GET_BUSGUID_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: UsbIoctl.h
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
-	usbioctl.h
api_name:
-	IOCTL_INTERNAL_USB_GET_BUSGUID_INFO
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_GET_BUSGUID_INFO IOCTL
The <b>IOCTL_INTERNAL_USB_GET_BUSGUID_INFO</b> IOCTL has been deprecated. Do not use.

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
| **Header** | usbioctl.h (include UsbIoctl.h) |