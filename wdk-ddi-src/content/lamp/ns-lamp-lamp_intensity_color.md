---
UID: NS.LAMP.LAMP_INTENSITY_COLOR
title: LAMP_INTENSITY_COLOR
author: windows-driver-content
description: This structure is the I/O parameter type of IOCTL_LAMP_GET_INTENSITY_COLOR and IOCTL_LAMP_SET_INTENSITY_COLOR.
old-location: stream\lamp_intensity_color.htm
old-project: stream
ms.assetid: F87AFCA5-651C-4782-9F6F-C0AFB09010CB
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: LAMP_INTENSITY_COLOR, LAMP_INTENSITY_COLOR
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
req.alt-api: LAMP_INTENSITY_COLOR
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

# LAMP_INTENSITY_COLOR structure



## -description
This structure is the I/O parameter type of <a href="..\lamp\ni-lamp-ioctl_lamp_get_intensity_color.md">IOCTL_LAMP_GET_INTENSITY_COLOR</a> and <a href="..\lamp\ni-lamp-ioctl_lamp_set_intensity_color.md">IOCTL_LAMP_SET_INTENSITY_COLOR</a>.



## -syntax

````
typedef struct LAMP_INTENSITY_COLOR {
  BYTE Red;
  BYTE Green;
  BYTE Blue;
} LAMP_INTENSITY_COLOR;
````


## -struct-fields

### -field Red

Red light intensity in percentage (0-100).


### -field Green

Green light intensity in percentage (0-100).


### -field Blue

Blue light intensity in percentage (0-100).


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