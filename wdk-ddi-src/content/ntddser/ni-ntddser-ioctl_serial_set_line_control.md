---
UID: NI:ntddser.IOCTL_SERIAL_SET_LINE_CONTROL
title: IOCTL_SERIAL_SET_LINE_CONTROL
author: windows-driver-content
description: The IOCTL_SERIAL_SET_LINE_CONTROL request sets the line control register (LCR). The line control register controls the data size, the number of stop bits, and the parity.
old-location: serports\ioctl_serial_set_line_control.htm
old-project: serports
ms.assetid: 0883b10c-1900-42b1-afc9-1e61effed111
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_SET_LINE_CONTROL, IOCTL_SERIAL_SET_LINE_CONTROL control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_LINE_CONTROL, serports.ioctl_serial_set_line_control, serref_70796be3-dbb8-4918-899d-d3750813aad3.xml
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
-	IOCTL_SERIAL_SET_LINE_CONTROL
product:
- Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_SET_LINE_CONTROL IOCTL
The <b>IOCTL_SERIAL_SET_LINE_CONTROL</b> request sets the line control register (LCR). The line control register controls the data size, the number of stop bits, and the parity.

To obtain the value of the line control register, a client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546582">IOCTL_SERIAL_GET_LINE_CONTROL</a> request.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The <b>AssociatedIrp.SystemBuffer</b> points to a client-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/jj680686">SERIAL_LINE_CONTROL</a> structure that is used to input line control information.

### Input Buffer Length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> is set to the size, in bytes, of a <b>SERIAL_LINE_CONTROL</b> structure.

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

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that the specified line control information is not valid.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddser.h (include Ntddser.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546582">IOCTL_SERIAL_GET_LINE_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj680686">SERIAL_LINE_CONTROL</a>