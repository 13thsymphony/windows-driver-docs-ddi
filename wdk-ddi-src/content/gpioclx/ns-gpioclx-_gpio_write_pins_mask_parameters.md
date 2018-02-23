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
ms.keywords: GPIO_WRITE_PINS_MASK_PARAMETERS structure [Parallel Ports], *PGPIO_WRITE_PINS_MASK_PARAMETERS, gpioclx/GPIO_WRITE_PINS_MASK_PARAMETERS, PGPIO_WRITE_PINS_MASK_PARAMETERS, GPIO_WRITE_PINS_MASK_PARAMETERS, PGPIO_WRITE_PINS_MASK_PARAMETERS structure pointer [Parallel Ports], GPIO.gpio_write_pins_mask_parameters, _GPIO_WRITE_PINS_MASK_PARAMETERS, gpioclx/PGPIO_WRITE_PINS_MASK_PARAMETERS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Gpioclx.h
apiname:
-	GPIO_WRITE_PINS_MASK_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PGPIO_WRITE_PINS_MASK_PARAMETERS, GPIO_WRITE_PINS_MASK_PARAMETERS"
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

`ClearMask`

A mask that specifies the GPIO pins to clear in this bank. If a bit in this mask is set to 1, the GPIO controller driver sets the corresponding GPIO pin to the value 0. If bit 0 of the mask is 1, the function clears pin 0; if bit 1 of the mask is 1, the function clears pin 1; and so on.

`Flags`

A set of flags to control the GPIO pin write operation. No flags are currently defined for this operation.

`Reserved`

Reserved for system use.

`SetMask`

A mask that specifies the GPIO pins to set in this bank. If a bit in this mask is set to 1, the GPIO controller driver sets the corresponding GPIO pin to the value 1. If N is the number of pins in this bank, the pins are numbered 0 to N–1. If bit 0 (the least significant bit) of the mask is 1, the function sets pin number 0; if bit 1 of the mask is 1, the function sets pin number 1; and so on.

## Remarks
The <i>WriteParameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439445">CLIENT_WriteGpioPinsUsingMask</a> event callback function is a pointer to a caller-allocated <b>GPIO_WRITE_PINS_MASK_PARAMETERS</b> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | gpioclx.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439445">CLIENT_WriteGpioPinsUsingMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_WRITE_PINS_MASK_PARAMETERS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>