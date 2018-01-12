---
UID: NE:d3dumddi._DXVAHDDDI_ROTATION
title: _DXVAHDDDI_ROTATION
author: windows-driver-content
description: Specifies the clockwise rotation of the display output surface.
old-location: display\dxvahdddi_rotation.htm
old-project: display
ms.assetid: 667f1c5e-c342-40b2-b215-2538669288cc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXVAHDDDI_ROTATION, DXVAHDDDI_ROTATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_ROTATION
req.alt-loc: D3dumddi.h
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
req.typenames: DXVAHDDDI_ROTATION
---

# _DXVAHDDDI_ROTATION enumeration



## -description
Specifies the clockwise rotation of the display output surface.



## -syntax

````
typedef enum _DXVAHDDDI_ROTATION { 
  DXVAHDDDI_ROTATION_IDENTITY  = 0,
  DXVAHDDDI_ROTATION_90        = 1,
  DXVAHDDDI_ROTATION_180       = 2,
  DXVAHDDDI_ROTATION_270       = 3
} DXVAHDDDI_ROTATION;
````


## -enum-fields

### -field DXVAHDDDI_ROTATION_IDENTITY

Indicates that rotation is 0 degrees—landscape mode.


### -field DXVAHDDDI_ROTATION_90

Indicates that rotation is 90 degrees clockwise—portrait mode.


### -field DXVAHDDDI_ROTATION_180

Indicates that rotation is 180 degrees clockwise—inverted landscape mode.


### -field DXVAHDDDI_ROTATION_270

Indicates that rotation is 270 degrees clockwise—inverted portrait mode.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>