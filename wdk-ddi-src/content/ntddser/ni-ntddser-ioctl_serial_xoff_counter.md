---
UID: NI:ntddser.IOCTL_SERIAL_XOFF_COUNTER
title: IOCTL_SERIAL_XOFF_COUNTER
author: windows-driver-content
description: The IOCTL_SERIAL_XOFF_COUNTER request sets an XOFF counter. An XOFF counter request supports clients that use software to emulate hardware handshake flow control.
old-location: serports\ioctl_serial_xoff_counter.htm
old-project: serports
ms.assetid: c24451cd-87d7-493d-83cb-2ee96590b8a3
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_XOFF_COUNTER, IOCTL_SERIAL_XOFF_COUNTER control code [Serial Ports], ntddser/IOCTL_SERIAL_XOFF_COUNTER, serports.ioctl_serial_xoff_counter, serref_ef42292d-d9d2-47be-b368-a696af5d0eea.xml
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
-	IOCTL_SERIAL_XOFF_COUNTER
product:
- Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_XOFF_COUNTER IOCTL
The <b>IOCTL_SERIAL_XOFF_COUNTER</b> request sets an <i>XOFF counter</i>. An XOFF counter request supports clients that use software to emulate hardware handshake flow control.

An XOFF counter request is synchronized with write requests. The driver sends a specified XOFF character, and completes the request after one of the following events occurs:
<ul>
<li>
A write request is received.

</li>
<li>
A timer expires (a time-out value is specified by the XOFF counter request).

</li>
<li>
The serial controller driver receives a number of characters that is greater than or equal to a count specified by the XOFF counter request.

</li>
</ul>For more information about the operation of an XOFF counter, see the description of the <b>SERIAL_XOFF_COUNTER</b> structure in the Ntddser.h header file in the Microsoft Windows Driver Kit (WDK).

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The <b>AssociatedIrp.SystemBuffer</b> points to a client-allocated <b>SERIAL_XOFF_COUNTER</b> structure that is used to input XOFF counter information.

### Input Buffer Length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> is set to the size, in bytes, of a <b>SERIAL_XOFF_COUNTER</b> structure.

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

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a> or to one of the following request-specific values:


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddser.h (include Ntddser.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546784">IOCTL_SERIAL_SET_XOFF</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546793">IOCTL_SERIAL_SET_XON</a>