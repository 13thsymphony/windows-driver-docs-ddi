---
UID: NS.gpioclx._GPIO_READ_PINS_PARAMETERS
title: GPIO_READ_PINS_PARAMETERS
author: windows-driver-content
description: The GPIO_READ_PINS_PARAMETERS structure describes a read operation on a group of general-purpose I/O (GPIO) pins.
old-location: gpio\gpio_read_pins_parameters.htm
old-project: GPIO
ms.assetid: D04C836E-C440-4AB9-BB44-7D1E8E0F681D
ms.author: windowsdriverdev
ms.date: 11/3/2017
ms.keywords: GPIO_READ_PINS_PARAMETERS, GPIO_READ_PINS_PARAMETERS, *PGPIO_READ_PINS_PARAMETERS
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
req.alt-api: GPIO_READ_PINS_PARAMETERS
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
req.iface: 
---

# GPIO_READ_PINS_PARAMETERS structure



## -description
<p>The <b>GPIO_READ_PINS_PARAMETERS</b> structure describes a read operation on a group of general-purpose I/O (GPIO) pins.</p>


## -syntax

````
typedef struct _GPIO_READ_PINS_PARAMETERS {
  BANK_ID              BankId;
  PPIN_NUMBER          PinNumberTable;
  ULONG                PinCount;
  PVOID                Buffer;
  GPIO_READ_PINS_FLAGS Flags;
  PVOID                Reserved;
} GPIO_READ_PINS_PARAMETERS, *PGPIO_READ_PINS_PARAMETERS;
````


## -struct-fields
<dl>

### -field BankId

<dd>
<p>The identifier for the bank of GPIO pins that contains the pins to read. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.</p>
</dd>

### -field PinNumberTable

<dd>
<p>A pointer to an array of bank-relative PIN_NUMBER values. Each array element specifies the number of a GPIO pin to read from. If this bank has N pins, the pins are numbered 0 to N–1. The number of elements in this array is specified by the <b>PinCount</b> member.</p>
</dd>

### -field PinCount

<dd>
<p>The number of elements in the <b>PinNumberTable</b> array.</p>
</dd>

### -field Buffer

<dd>
<p>A pointer to a buffer to hold the values that the GPIO controller driver reads from the GPIO pins that are specified by the <b>PinNumberTable</b> array. Array element 0 specifies the GPIO pin whose value is saved to bit 0 (the least significant bit) in the buffer, array element 1 specifies the GPIO pin whose value is saved to bit 1 in the buffer, and so on.</p>
</dd>

### -field Flags

<dd>
<p>A set of flags to control the GPIO pin read operation. If the <b>WriteConfiguredPins</b> flag bit is set, the GPIO controller driver can read from a GPIO pin that is configured for write operations.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for system use.</p>
</dd>
</dl>

## -remarks
<p>The <i>ReadParameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439404">CLIENT_ReadGpioPins</a> event callback function is a pointer to a caller-allocated <b>GPIO_READ_PINS_PARAMETERS</b> structure. All of the pins that this function reads are part of the same bank of GPIO pins.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439404">CLIENT_ReadGpioPins</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_READ_PINS_PARAMETERS structure%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
