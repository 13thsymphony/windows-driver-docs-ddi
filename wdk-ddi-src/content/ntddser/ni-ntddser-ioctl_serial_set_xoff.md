---
UID: NI:ntddser.IOCTL_SERIAL_SET_XOFF
title: IOCTL_SERIAL_SET_XOFF
author: windows-driver-content
description: The IOCTL_SERIAL_SET_XOFF request emulates the reception of an XOFF (transmit off) character.
old-location: serports\ioctl_serial_set_xoff.htm
old-project: serports
ms.assetid: cfddecbd-e225-484f-ba5c-6223a724b414
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_SET_XOFF, IOCTL_SERIAL_SET_XOFF control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_XOFF, serports.ioctl_serial_set_xoff, serref_a2b3591a-cd26-4073-a7ab-af7f2b3f43b6.xml
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
-	IOCTL_SERIAL_SET_XOFF
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_SET_XOFF IOCTL
The <b>IOCTL_SERIAL_SET_XOFF</b> request emulates the reception of an XOFF (transmit off) character. The request stops reception of data. If automatic XON/XOFF flow control is not set, then a client <u>must</u> use a subsequent <a href="https://msdn.microsoft.com/library/windows/hardware/ff546793">IOCTL_SERIAL_SET_XON</a> request to restart reception of data.

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

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546793">IOCTL_SERIAL_SET_XON</a>