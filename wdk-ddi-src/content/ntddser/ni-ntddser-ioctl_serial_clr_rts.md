---
UID: NI:ntddser.IOCTL_SERIAL_CLR_RTS
title: IOCTL_SERIAL_CLR_RTS
author: windows-driver-content
description: The IOCTL_SERIAL_CLR_RTS request clears the request to send (RTS) control signal.
old-location: serports\ioctl_serial_clr_rts.htm
old-project: serports
ms.assetid: 7ecb357f-ba84-4b3d-b6db-73f6682988b8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_CLR_RTS, IOCTL_SERIAL_CLR_RTS control code [Serial Ports], ntddser/IOCTL_SERIAL_CLR_RTS, serports.ioctl_serial_clr_rts, serref_c6ddd78f-7cea-4358-9c02-9c211399f6c8.xml
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
-	IOCTL_SERIAL_CLR_RTS
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_CLR_RTS IOCTL
The <b>IOCTL_SERIAL_CLR_RTS</b> request clears the <i>request to send</i> (RTS) control signal.

To set RTS, a client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546760">IOCTL_SERIAL_SET_RTS</a> request.

If the handshake flow control of the device is configured to automatically use RTS, a client cannot clear or set RTS.

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


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddser.h (include Ntddser.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546760">IOCTL_SERIAL_SET_RTS</a>