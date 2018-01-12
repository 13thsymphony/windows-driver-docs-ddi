---
UID: NS:lamp.LAMP_CAPABILITIES_WHITE
title: LAMP_CAPABILITIES_WHITE
author: windows-driver-content
description: This structure is the I/O parameter type of IOCTL_LAMP_{GET|SET}_INTENSITY_WHITE.
old-location: stream\lamp_capabilities_white.htm
old-project: stream
ms.assetid: F407B953-8B03-4053-A5F4-3E96E9F9645E
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: LAMP_CAPABILITIES_WHITE, LAMP_CAPABILITIES_WHITE
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
req.alt-api: LAMP_CAPABILITIES_WHITE
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
req.typenames: LAMP_CAPABILITIES_WHITE
---

# LAMP_CAPABILITIES_WHITE structure



## -description
This structure is the I/O parameter type of <b>IOCTL_LAMP_{GET|SET}_INTENSITY_WHITE</b>.



## -syntax

````
typedef struct LAMP_CAPABILITIES_WHITE {
  BOOLEAN IsLightIntensityAdjustable;
} LAMP_CAPABILITIES_WHITE;
````


## -struct-fields

### -field IsLightIntensityAdjustable

If this field evaluates <b>TRUE</b>, a client can get/set light intensity by calling <a href="..\lamp\ni-lamp-ioctl_lamp_get_intensity_white.md">IOCTL_LAMP_GET_INTENSITY_WHITE</a>  and <a href="..\lamp\ni-lamp-ioctl_lamp_set_intensity_white.md">IOCTL_LAMP_SET_INTENSITY_WHITE</a>.


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