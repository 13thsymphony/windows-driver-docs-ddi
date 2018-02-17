---
UID: NS:gpioclx._GPIO_MASK_INTERRUPT_PARAMETERS
title: "_GPIO_MASK_INTERRUPT_PARAMETERS"
author: windows-driver-content
description: The GPIO_MASK_INTERRUPT_PARAMETERS structure describes a set of general-purpose I/O (GPIO) interrupt pins to mask.
old-location: gpio\gpio_mask_interrupt_parameters.htm
old-project: GPIO
ms.assetid: E7975BAE-4255-4D07-A747-481D210D1244
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO_MASK_INTERRUPT_PARAMETERS structure [Parallel Ports], gpioclx/PGPIO_MASK_INTERRUPT_PARAMETERS, _GPIO_MASK_INTERRUPT_PARAMETERS, PGPIO_MASK_INTERRUPT_PARAMETERS, *PGPIO_MASK_INTERRUPT_PARAMETERS, PGPIO_MASK_INTERRUPT_PARAMETERS structure pointer [Parallel Ports], gpioclx/GPIO_MASK_INTERRUPT_PARAMETERS, GPIO.gpio_mask_interrupt_parameters, GPIO_MASK_INTERRUPT_PARAMETERS
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
-	GPIO_MASK_INTERRUPT_PARAMETERS
product: Windows
targetos: Windows
req.typenames: GPIO_MASK_INTERRUPT_PARAMETERS, *PGPIO_MASK_INTERRUPT_PARAMETERS
---

# _GPIO_MASK_INTERRUPT_PARAMETERS structure
The <b>GPIO_MASK_INTERRUPT_PARAMETERS</b> structure describes a set of general-purpose I/O (GPIO) interrupt pins to mask.

## Syntax
````
typedef struct _GPIO_MASK_INTERRUPT_PARAMETERS {
  BANK_ID BankId;
  ULONG64 PinMask;
  ULONG64 FailedMask;
} GPIO_MASK_INTERRUPT_PARAMETERS, *PGPIO_MASK_INTERRUPT_PARAMETERS;
````

## Members


`BankId`

The identifier for the bank of GPIO pins that contains the interrupts to mask. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.

`FailedMask`

A 64-bit mask that identifies the GPIO pins that could not be masked. If the GPIO controller driver fails to mask a bit that is indicated in the <b>PinMask</b> member, the driver sets the corresponding bit in the <b>FailedMask</b> member to mark this failure. If all pins specified in <b>PinMask</b> are successfully masked, the driver sets <b>FailedMask</b> to zero. For more information, see Remarks.

`PinMask`

A 64-bit mask to indicate which interrupt pins to mask in the specified bank. This mask affects only GPIO pins that are configured as interrupt request inputs. A bit in the mask that is set to 1 identifies a pin that is to be masked. All other bits in the mask are 0. If N is the number of pins in this bank, the pins are numbered 0 to N–1. Bit 0 (the least significant bit) in the mask represents pin 0, bit 1 represents pin 1, and so on.

## Remarks
The <i>MaskParameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439380">CLIENT_MaskInterrupts</a> event callback function is a pointer to a caller-allocated <b>GPIO_MASK_INTERRUPT_PARAMETERS</b> structure. This function affects only GPIO pins that are configured as interrupt inputs and that are part of the specified bank of GPIO pins.

GPIO controllers that have memory-mapped registers are expected to always succeed in setting the interrupt mask to the requested value. The <b>FailedMask</b> member is primarily intended for use by GPIO controllers that are not memory-mapped.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | gpioclx.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439380">CLIENT_MaskInterrupts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_MASK_INTERRUPT_PARAMETERS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>