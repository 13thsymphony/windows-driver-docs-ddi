---
UID: NI:ntddser.IOCTL_SERIAL_RESET_DEVICE
title: IOCTL_SERIAL_RESET_DEVICE
author: windows-driver-content
description: The IOCTL_SERIAL_RESET_DEVICE request resets a serial device.
old-location: serports\ioctl_serial_reset_device.htm
old-project: serports
ms.assetid: af7482b4-4622-40b7-af7a-c952813e7095
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_RESET_DEVICE, IOCTL_SERIAL_RESET_DEVICE control code [Serial Ports], ntddser/IOCTL_SERIAL_RESET_DEVICE, serports.ioctl_serial_reset_device, serref_8c489e42-94d9-4a10-9336-dae4adea904a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
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
-	Ntddser.h
api_name:
-	IOCTL_SERIAL_RESET_DEVICE
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_RESET_DEVICE IOCTL
The <b>IOCTL_SERIAL_RESET_DEVICE</b> request resets a serial device.

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
The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddser.h (include Ntddser.h) |