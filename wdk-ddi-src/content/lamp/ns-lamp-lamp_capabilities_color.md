---
UID: NS.LAMP.LAMP_CAPABILITIES_COLOR
title: LAMP_CAPABILITIES_COLOR
author: windows-driver-content
description: This structure is the I/O parameter type of IOCTL_LAMP_{GET|SET}_INTENSITY_COLOR.
old-location: stream\lamp_capabilities_color.htm
old-project: stream
ms.assetid: BCF2171C-93CB-4DAC-AA78-C272D5445F99
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: LAMP_CAPABILITIES_COLOR, LAMP_CAPABILITIES_COLOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: lamp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: LAMP_CAPABILITIES_COLOR
req.alt-loc: lamp.h
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
---

# LAMP_CAPABILITIES_COLOR structure



## -description
This structure is the I/O parameter type of <b>IOCTL_LAMP_{GET|SET}_INTENSITY_COLOR</b>.



## -syntax

````
typedef struct LAMP_CAPABILITIES_COLOR {
  BOOLEAN IsSupported;
  BOOLEAN IsLightIntensityAdjustable;
} LAMP_CAPABILITIES_COLOR;
````


## -struct-fields

### -field IsSupported

<b>TRUE</b> if the device can emit color light; <b>FALSE</b> otherwise.


### -field IsLightIntensityAdjustable

If <b>IsSupported</b> evaluates to <b>TRUE</b> (the driver is capable of emitting color light) and this field evaluates to <b>TRUE</b>, a client can get/set light intensity of a color lamp by calling <a href="..\lamp\ni-lamp-ioctl_lamp_get_intensity_color.md">IOCTL_LAMP_GET_INTENSITY_COLOR</a> and <a href="..\lamp\ni-lamp-ioctl_lamp_set_intensity_color.md">IOCTL_LAMP_SET_INTENSITY_COLOR</a>.



## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Lamp.h</dt>
</dl>
</td>
</tr>
</table>