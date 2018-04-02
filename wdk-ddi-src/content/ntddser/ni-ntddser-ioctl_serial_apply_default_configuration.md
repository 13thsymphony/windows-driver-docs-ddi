---
UID: NI:ntddser.IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION
title: IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION
author: windows-driver-content
description: The IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION control code configures the serial port to use the default hardware settings for the serial controller device.
old-location: serports\ioctl_serial_apply_default_configuration.htm
old-project: serports
ms.assetid: 59AA6029-906C-480F-8F18-82C271A2BE88
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION, IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION control code [Serial Ports], ntddser/IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION, serports.ioctl_serial_apply_default_configuration
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
-	IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION
product:
- Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION IOCTL
The <b>IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</b> control code configures the serial port to use the default hardware settings for the serial controller device. These settings are obtained from the ACPI resource descriptor for the serial controller device. For more information, see the <i>Advanced Configuration and Power Interface Specification, Revision 5.0</i>, at the <a href="http://www.acpi.info">ACPI</a> website.

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

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">generic status values for serial device control requests</a>. A status of STATUS_NOT_IMPLEMENTED indicates that the serial port does not support a default configuration. In this case, the client must use the other <b>IOCTL_SERIAL_<i>XXX</i></b> I/O control requests to explicitly configure the serial port.

## Remarks
The client (application or peripheral device driver) sends this IOCTL to configure the serial port to use a set of default connection settings. These settings include connection-specific hardware parameters such as the baud rate, time-out values, and flow-control flags.

This IOCTL is supported by versions 1 and 2 of the serial framework extension (SerCx and SerCx2). Serial.sys, which manages the named serial ports (COM1, COM2, and so on) on a PC, does not support this IOCTL.

If a serial port does not support this IOCTL, the client must explicitly specify the connection settings for the port. That is, the client must send an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546672">IOCTL_SERIAL_SET_BAUD_RATE</a> request to set the baud rate, send an <a href="https://msdn.microsoft.com/library/windows/hardware/ff544126">IOCTL_SERIAL_SET_TIMEOUTS</a> request to set the time-out intervals, and so on.

Immediately after a client opens a serial port, the client should assume that the port is configured in an unknown, uninitialized state rather than in some known, default state.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | ntddser.h (include Ntddser.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546672">IOCTL_SERIAL_SET_BAUD_RATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544126">IOCTL_SERIAL_SET_TIMEOUTS</a>