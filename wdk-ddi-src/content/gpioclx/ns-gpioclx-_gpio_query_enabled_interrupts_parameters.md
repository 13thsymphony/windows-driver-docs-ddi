---
UID: NS.GPIOCLX._GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS
title: _GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS
author: windows-driver-content
description: The GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS structure indicates which interrupt pins in a bank of general-purpose I/O (GPIO) pins are enabled.
old-location: gpio\gpio_query_enabled_interrupts_parameters.htm
old-project: GPIO
ms.assetid: CC2EEF26-CCC0-4093-8A44-12FF1EDD2FF9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS, GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS, *PGPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gpioclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS
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
---

# _GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS structure



## -description
The <b>GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS</b> structure indicates which interrupt pins in a bank of general-purpose I/O (GPIO) pins are enabled.



## -syntax

````
typedef struct _GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS {
  BANK_ID BankId;
  ULONG64 EnabledMask;
} GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS, *PGPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS;
````


## -struct-fields

### -field BankId

The identifier for the bank of GPIO pins to query for enabled interrupts. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field EnabledMask

A 64-bit mask that indicates which interrupts are enabled in the specified bank. A bit in the mask that is set to 1 identifies an interrupt pin that is enabled for interrupts. All other bits in the mask are 0. If N is the number of pins in this bank, the pins are numbered 0 to N–1. Bit 0 (the least significant bit) in the mask represents pin 0, bit 1 represents pin 1, and so on.


## -remarks
The <i>QueryEnabledParameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265184">CLIENT_QueryEnabledInterrupts</a> event callback function is a pointer to a caller-allocated <b>GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS</b> structure. Before calling this function, the caller writes a bank ID to the <b>BankId</b> member of this structure to specify which bank of GPIO pins to query. The function writes a mask value to the <b>EnabledMask</b> member of this structure to indicate which interrupts are enabled in the specified bank.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 8.1.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265184">CLIENT_QueryEnabledInterrupts</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

