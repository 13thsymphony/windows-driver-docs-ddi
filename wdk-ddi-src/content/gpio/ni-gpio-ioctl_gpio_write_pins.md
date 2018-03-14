---
UID: NI:gpio.IOCTL_GPIO_WRITE_PINS
title: IOCTL_GPIO_WRITE_PINS
author: windows-driver-content
description: The IOCTL_GPIO_WRITE_PINS I/O control code enables a client of the general-purpose I/O (GPIO) controller to write to a set of GPIO pins that are configured as outputs.
old-location: gpio\ioctl_gpio_write_pins.htm
old-project: GPIO
ms.assetid: 579462C6-2C0B-41AC-836D-2D3448080AD8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GPIO.ioctl_gpio_write_pins, IOCTL_GPIO_WRITE_PINS, IOCTL_GPIO_WRITE_PINS control code [Parallel Ports], gpio/IOCTL_GPIO_WRITE_PINS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: gpio.h
req.include-header: 
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
-	Gpio.h
api_name:
-	IOCTL_GPIO_WRITE_PINS
product: Windows
targetos: Windows
req.typenames: GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
---

# IOCTL_GPIO_WRITE_PINS IOCTL
The <b>IOCTL_GPIO_WRITE_PINS</b> I/O control code enables a client of the general-purpose I/O (GPIO) controller to write to a set of GPIO pins that are configured as outputs. Typically, the clients of a GPIO controller are drivers for peripheral devices that connect to GPIO pins.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The input buffer.

### Input Buffer Length
The input buffer should be large enough to contain data for all of the GPIO pins that are part of the target connection to which the client sends the request. For example, if the GPIO controller hardware implements 64 GPIO pins, and the client opens a connection to three of these GPIO pins, a one-byte buffer is sufficiently large to contain the three 1-bit values to write to the three pins in the connection.

### Output Buffer
The output buffer contains the same data as the input buffer (because the <i>TransferType</i> for this IOCTL is METHOD_BUFFERED).

### Output Buffer Length
Same as the input buffer.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the operation is successful, the controller driver sets the <b>Status</b> member to STATUS_SUCCESS, and sets the <b>Information</b> member to the total number of bytes transferred during the requested operation. If the operation transfers N bits, the number of bytes transferred is (N + 7) / 8. (That is, 7 is added to N to round up to the next byte boundary before the integer division by 8.)

If this request fails, the <b>Status</b> member is set to an error code and no data is read from the GPIO pins. The requested operation might fail for various reasons, which can include invalid client input, low resources, and device malfunction.

If the input buffer is not large enough to contain one bit of data for each GPIO pin in the target connection, the <b>Status</b> member is set to STATUS_BUFFER_TOO_SMALL. If the GPIO pins in the target connection are configured as inputs, the <b>Status</b> member is set to STATUS_GPIO_OPERATION_DENIED.

## Remarks
This request writes to all of the GPIO pins that are part of the target connection to which the client sends the request. For example, if the connection has three pins, bits 0, 1, and 2 from the input buffer are written to these three pins. The three pins in this example connection might map to GPIO pins 7, 8, and 23 in the GPIO controller hardware. If so, bit 0 (the least significant bit) in the buffer is written to GPIO pin 7, bit 1 in the buffer is written to GPIO pin 8, and bit 2 in the buffer is written to GPIO pin 23.

When the client opens a connection to a target GPIO device, all of the GPIO pins in this connection are configured either as inputs or as outputs. An <b>IOCTL_GPIO_WRITE_PINS</b> request can succeed only if the target pins are outputs.

The client sends this I/O control request to the file object for the target device. The file object is a <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure that represents a logical connection to the target. <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn550976">Kernel-mode driver framework</a> (KMDF) drivers call the <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a> method to open this connection. <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/overview-of-the-umdf">User-mode driver framework</a> (UMDF) drivers call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560273">IWDFRemoteTarget::OpenFileByName</a> method to open the connection.

For code examples that show how to use the <b>IOCTL_GPIO_WRITE_PINS</b> request to write to a set of GPIO I/O pins, see the following topics:

<a href="https://msdn.microsoft.com/02F6431C-7B55-4DFB-9792-4A72F0268C76">Connecting a KMDF Driver to GPIO I/O Pins</a>
<a href="https://msdn.microsoft.com/6869D298-5EB4-4991-A67F-F4398CE2D191">Connecting a UMDF Driver to GPIO I/O Pins</a>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | gpio.h |

## See Also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560273">IWDFRemoteTarget::OpenFileByName</a>



<a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20IOCTL_GPIO_WRITE_PINS control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>