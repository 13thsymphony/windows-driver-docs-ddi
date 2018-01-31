---
UID : NE:gpioclx._GPIO_CONNECT_IO_PINS_MODE
title : "_GPIO_CONNECT_IO_PINS_MODE"
author : windows-driver-content
description : The GPIO_CONNECT_IO_PINS_MODE enumeration indicates whether a set of general-purpose I/O (GPIO) pins is configured as inputs or outputs.
old-location : gpio\gpio_connect_io_pins_mode.htm
old-project : GPIO
ms.assetid : 17E98D35-8C63-4EEC-B8DD-896FA2B084A8
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : GPIO_CONNECT_IO_PINS_MODE, ConnectModeOutput, gpioclx/ConnectModeInput, ConnectModeMaximum, gpioclx/ConnectModeInvalid, GPIO_CONNECT_IO_PINS_MODE enumeration [Parallel Ports], gpioclx/GPIO_CONNECT_IO_PINS_MODE, gpioclx/ConnectModeMaximum, ConnectModeInput, ConnectModeInvalid, gpioclx/ConnectModeOutput, *PGPIO_CONNECT_IO_PINS_MODE, _GPIO_CONNECT_IO_PINS_MODE, GPIO.gpio_connect_io_pins_mode
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : gpioclx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PGPIO_CONNECT_IO_PINS_MODE, GPIO_CONNECT_IO_PINS_MODE"
---

# _GPIO_CONNECT_IO_PINS_MODE Enumeration
The <b>GPIO_CONNECT_IO_PINS_MODE</b> enumeration indicates whether a set of general-purpose I/O (GPIO) pins is configured as inputs or outputs.

## Syntax
````
typedef enum _GPIO_CONNECT_IO_PINS_MODE { 
  ConnectModeInvalid,
  ConnectModeInput,
  ConnectModeOutput,
  ConnectModeMaximum  = ConnectModeOutput
} GPIO_CONNECT_IO_PINS_MODE;
````

## Constants

<table>

<tr>
<td>ConnectModeInput</td>
<td>This set of GPIO pins is configured as data inputs.</td>
</tr>

<tr>
<td>ConnectModeInvalid</td>
<td>The connection mode (input or output) for this set of GPIO pins is uninitialized.</td>
</tr>

<tr>
<td>ConnectModeMaximum</td>
<td>The maximum value in the enumeration.</td>
</tr>

<tr>
<td>ConnectModeOutput</td>
<td>This set of GPIO pins is configured as data outputs.</td>
</tr>
</table>

## Remarks

The <b>ConnectMode</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439502">GPIO_CONNECT_IO_PINS_PARAMETERS</a> structure contains a <b>GPIO_CONNECT_IO_PINS_MODE</b> enumeration constant.

The <b>ConnectModeInput</b> enumeration constant labels a set of GPIO pins that can be read by an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406483">IOCTL_GPIO_READ_PINS</a> request. <b>ConnectModeOutput</b> labels a set of GPIO pins that can be written to by an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406487">IOCTL_GPIO_WRITE_PINS</a> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | gpioclx.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439502">GPIO_CONNECT_IO_PINS_PARAMETERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406487">IOCTL_GPIO_WRITE_PINS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406483">IOCTL_GPIO_READ_PINS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_CONNECT_IO_PINS_MODE enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>