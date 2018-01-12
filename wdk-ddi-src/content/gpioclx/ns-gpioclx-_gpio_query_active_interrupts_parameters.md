---
UID: NS:gpioclx._GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
title: _GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
author: windows-driver-content
description: The GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS structure describes a set of general-purpose I/O (GPIO) interrupt pins to query for their enabled and active states.
old-location: gpio\gpio_query_active_interrupts_parameters.htm
old-project: GPIO
ms.assetid: A3111B9C-319F-4560-B5A9-5CA6523AD935
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS, GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS, *PGPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
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
req.alt-api: GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
req.alt-loc: Gpioclx.h
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
req.typenames: GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS, *PGPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
---

# _GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS structure



## -description
The <b>GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS</b> structure describes a set of general-purpose I/O (GPIO) interrupt pins to query for their enabled and active states.



## -syntax

````
typedef struct _GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS {
  BANK_ID BankId;
  ULONG64 EnabledMask;
  ULONG64 ActiveMask;
} GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS, *PGPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS;
````


## -struct-fields

### -field BankId

The identifier for the bank of GPIO pins that contains the interrupts to query. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field EnabledMask

A ULONG64 variable to which the GPIO controller driver writes a 64-bit mask to indicate which interrupt pins are enabled in the specified bank. A bit in the mask that is set to 1 identifies a pin that is configured as an interrupt and that is enabled. All other bits in the mask are 0. If N is the number of pins in this bank, the pins are numbered 0 to N–1. Bit 0 (the least significant bit) in the mask represents pin 0, bit 1 represents pin 1, and so on.


### -field ActiveMask

A ULONG64 variable to which the GPIO controller driver writes a 64-bit mask to indicate which interrupt pins are active in the specified bank. A bit in the mask that is set to 1 identifies a pin that is configured as an interrupt and that is active. All other bits in the mask are 0.


## -remarks
The <i>QueryActiveParameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439395">CLIENT_QueryActiveInterrupts</a> event callback function is a pointer to a caller-allocated <b>GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS</b> structure. This function queries only GPIO pins that are configured as interrupt inputs. All other GPIO pins in the specified bank are represented as zeros in the <b>EnabledMask</b> and <b>ActiveMask</b> members of the structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Gpioclx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439395">CLIENT_QueryActiveInterrupts</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

