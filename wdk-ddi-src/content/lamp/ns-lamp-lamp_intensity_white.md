---
UID: NS.LAMP.LAMP_INTENSITY_WHITE
title: LAMP_INTENSITY_WHITE
author: windows-driver-content
description: This structure is the I/O parameter type of IOCTL_LAMP_GET_INTENSITY_WHITE and IOCTL_LAMP_SET_INTENSITY_WHITE.
old-location: stream\lamp_intensity_white.htm
old-project: stream
ms.assetid: BDE53311-589F-4458-9510-1B02F1BD0289
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: LAMP_INTENSITY_WHITE, LAMP_INTENSITY_WHITE
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
req.alt-api: LAMP_INTENSITY_WHITE
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

# LAMP_INTENSITY_WHITE structure



## -description
This structure is the I/O parameter type of <a href="stream.ioctl_lamp_get__intensity_white">IOCTL_LAMP_GET_INTENSITY_WHITE</a> and <a href="..\lamp\ni-lamp-ioctl_lamp_set_intensity_white.md">IOCTL_LAMP_SET_INTENSITY_WHITE</a>.



## -syntax

````
typedef struct LAMP_INTENSITY_WHITE {
  BYTE Value;
} LAMP_INTENSITY_WHITE;
````


## -struct-fields

### -field Value

White light intensity in percentage (0-100).


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