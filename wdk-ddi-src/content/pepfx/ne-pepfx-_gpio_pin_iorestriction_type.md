---
UID: NE.pepfx._GPIO_PIN_IORESTRICTION_TYPE
title: _GPIO_PIN_IORESTRICTION_TYPE
author: windows-driver-content
description: The GPIO_PIN_IORESTRICTION_TYPE enumeration describes the functions that a GPIO pin is limited to performing.
old-location: kernel\gpio_pin_iorestriction_type.htm
old-project: kernel
ms.assetid: 381A59EE-BA1C-4810-842B-1D3E4D964486
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _GPIO_PIN_IORESTRICTION_TYPE, GPIO_PIN_IORESTRICTION_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GPIO_PIN_IORESTRICTION_TYPE
req.alt-loc: pepfx.h
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
---

# _GPIO_PIN_IORESTRICTION_TYPE enumeration



## -description
The <b>GPIO_PIN_IORESTRICTION_TYPE</b> enumeration describes the functions that a GPIO pin is limited to performing.



## -syntax

````
typedef enum _GPIO_PIN_IORESTRICTION_TYPE { 
  IoRestrictionNone,
  IoRestrictionInputOnly,
  IoRestrictionOutputOnly,
  IoRestrictionNoneAndPreserve
} GPIO_PIN_IORESTRICTION_TYPE;
````


## -enum-fields

### -field IoRestrictionNone

Indicates that the GPIO pin is not restricted to either input or output. When no IO restriction is described, it is assumed to be <b>IoRestrictionNone</b>. 


### -field IoRestrictionInputOnly

Indicates that the GPIO pin is restricted to input. 


### -field IoRestrictionOutputOnly

Indicates that the GPIO pin is restricted to output. 


### -field IoRestrictionNoneAndPreserve

Indicates that the GPIO pin is not restricted to either input or output and that the mode should be preserved when the driver is unloaded. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 10.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>