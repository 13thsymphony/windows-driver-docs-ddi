---
UID: NS:gpioclx._GPIO_WRITE_PINS_MASK_PARAMETERS
title: "_GPIO_WRITE_PINS_MASK_PARAMETERS"
author: windows-driver-content
description: The GPIO_WRITE_PINS_MASK_PARAMETERS structure describes a write operation on a bank of general-purpose I/O (GPIO) pins.
old-location: gpio\gpio_write_pins_mask_parameters.htm
old-project: GPIO
ms.assetid: 5861FC4E-9902-4839-9829-B04F6AED61FE
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGPIO_WRITE_PINS_MASK_PARAMETERS, GPIO.gpio_write_pins_mask_parameters, GPIO_WRITE_PINS_MASK_PARAMETERS, GPIO_WRITE_PINS_MASK_PARAMETERS structure [Parallel Ports], PGPIO_WRITE_PINS_MASK_PARAMETERS, PGPIO_WRITE_PINS_MASK_PARAMETERS structure pointer [Parallel Ports], _GPIO_WRITE_PINS_MASK_PARAMETERS, gpioclx/GPIO_WRITE_PINS_MASK_PARAMETERS, gpioclx/PGPIO_WRITE_PINS_MASK_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Gpioclx.h
api_name:
-	GPIO_WRITE_PINS_MASK_PARAMETERS
product: Windows
targetos: Windows
req.typenames: GPIO_WRITE_PINS_MASK_PARAMETERS, *PGPIO_WRITE_PINS_MASK_PARAMETERS
---

# _GPIO_WRITE_PINS_MASK_PARAMETERS structure
The <b>GPIO_WRITE_PINS_MASK_PARAMETERS</b> structure describes a write operation on a bank of general-purpose I/O (GPIO) pins.

## Syntax
````
typedef struct _GPIO_WRITE_PINS_MASK_PARAMETERS {
  BANK_ID               BankId;
  ULONG64               SetMask;
  ULONG64               ClearMask;
  GPIO_WRITE_PINS_FLAGS Flags;
  PVOID                 Reserved;
} GPIO_WRITE_PINS_MASK_PARAMETERS, *PGPIO_WRITE_PINS_MASK_PARAMETERS;
````

## Members


`BankId`

The identifier for this bank of GPIO pins. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.

`SetMask`

A mask that specifies the GPIO pins to set in this bank. If a bit in this mask is set to 1, the GPIO controller driver sets the corresponding GPIO pin to the value 1. If N is the number of pins in this bank, the pins are numbered 0 to N–1. If bit 0 (the least significant bit) of the mask is 1, the function sets pin number 0; if bit 1 of the mask is 1, the function sets pin number 1; and so on.

`ClearMask`

A mask that specifies the GPIO pins to clear in this bank. If a bit in this mask is set to 1, the GPIO controller driver sets the corresponding GPIO pin to the value 0. If bit 0 of the mask is 1, the function clears pin 0; if bit 1 of the mask is 1, the function clears pin 1; and so on.

`Flags`

A set of flags to control the GPIO pin write operation. No flags are currently defined for this operation.

`Reserved`

Reserved for system use.

## Remarks
The <i>WriteParameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439445">CLIENT_WriteGpioPinsUsingMask</a> event callback function is a pointer to a caller-allocated <b>GPIO_WRITE_PINS_MASK_PARAMETERS</b> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | gpioclx.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439445">CLIENT_WriteGpioPinsUsingMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>