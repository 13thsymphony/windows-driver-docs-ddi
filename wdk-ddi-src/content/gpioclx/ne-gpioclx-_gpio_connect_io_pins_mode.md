---
UID: NE:gpioclx._GPIO_CONNECT_IO_PINS_MODE
title: "_GPIO_CONNECT_IO_PINS_MODE"
author: windows-driver-content
description: The GPIO_CONNECT_IO_PINS_MODE enumeration indicates whether a set of general-purpose I/O (GPIO) pins is configured as inputs or outputs.
old-location: gpio\gpio_connect_io_pins_mode.htm
old-project: GPIO
ms.assetid: 17E98D35-8C63-4EEC-B8DD-896FA2B084A8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGPIO_CONNECT_IO_PINS_MODE, ConnectModeInput, ConnectModeInvalid, ConnectModeMaximum, ConnectModeOutput, GPIO.gpio_connect_io_pins_mode, GPIO_CONNECT_IO_PINS_MODE, GPIO_CONNECT_IO_PINS_MODE enumeration [Parallel Ports], _GPIO_CONNECT_IO_PINS_MODE, gpioclx/ConnectModeInput, gpioclx/ConnectModeInvalid, gpioclx/ConnectModeMaximum, gpioclx/ConnectModeOutput, gpioclx/GPIO_CONNECT_IO_PINS_MODE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: gpioclx.h
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
req.irql: See Remarks.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Gpioclx.h
api_name:
-	GPIO_CONNECT_IO_PINS_MODE
product: Windows
targetos: Windows
req.typenames: GPIO_CONNECT_IO_PINS_MODE, *PGPIO_CONNECT_IO_PINS_MODE
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
                    <td>ConnectModeInvalid</td>
                    <td>The connection mode (input or output) for this set of GPIO pins is uninitialized.</td>
                </tr>
            
                <tr>
                    <td>ConnectModeInput</td>
                    <td>This set of GPIO pins is configured as data inputs.</td>
                </tr>
            
                <tr>
                    <td>ConnectModeOutput</td>
                    <td>This set of GPIO pins is configured as data outputs.</td>
                </tr>
            
                <tr>
                    <td>ConnectModeMaximum</td>
                    <td>The maximum value in the enumeration.</td>
                </tr>
</table>

## Remarks

The <b>ConnectMode</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439502">GPIO_CONNECT_IO_PINS_PARAMETERS</a> structure contains a <b>GPIO_CONNECT_IO_PINS_MODE</b> enumeration constant.

The <b>ConnectModeInput</b> enumeration constant labels a set of GPIO pins that can be read by an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406483">IOCTL_GPIO_READ_PINS</a> request. <b>ConnectModeOutput</b> labels a set of GPIO pins that can be written to by an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406487">IOCTL_GPIO_WRITE_PINS</a> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | gpioclx.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406487">IOCTL_GPIO_WRITE_PINS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406483">IOCTL_GPIO_READ_PINS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439502">GPIO_CONNECT_IO_PINS_PARAMETERS</a>