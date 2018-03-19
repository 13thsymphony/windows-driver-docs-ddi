---
UID: NI:ntddser.IOCTL_SERIAL_SET_BREAK_OFF
title: IOCTL_SERIAL_SET_BREAK_OFF
author: windows-driver-content
description: The IOCTL_SERIAL_SET_BREAK_OFF request sets the line control break signal inactive.
old-location: serports\ioctl_serial_set_break_off.htm
old-project: serports
ms.assetid: aa64da58-cb50-485e-afbc-3a0408b4ecf2
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_SET_BREAK_OFF, IOCTL_SERIAL_SET_BREAK_OFF control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_BREAK_OFF, serports.ioctl_serial_set_break_off, serref_1a347f28-6dfb-4b5d-afb8-9bb8ffad9f36.xml
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
-	IOCTL_SERIAL_SET_BREAK_OFF
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_SET_BREAK_OFF IOCTL
The <b>IOCTL_SERIAL_SET_BREAK_OFF</b> request sets the line control break signal inactive.

To set the line control break signal active, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_break_on.md">IOCTL_SERIAL_SET_BREAK_ON</a> request.

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

The <b>Status</b> member is to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddser.h (include Ntddser.h) |

## See Also

<a href="..\ntddser\ni-ntddser-ioctl_serial_set_break_on.md">IOCTL_SERIAL_SET_BREAK_ON</a>