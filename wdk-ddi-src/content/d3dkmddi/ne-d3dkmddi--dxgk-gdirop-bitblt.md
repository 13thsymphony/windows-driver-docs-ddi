---
UID: NE.d3dkmddi._DXGK_GDIROP_BITBLT
title: DXGK_GDIROP_BITBLT
author: windows-driver-content
description: The DXGK_GDIROP_COLORFILL enumeration indicates the type of GDI raster operation (ROP) to implement in a GDI hardware-accelerated bit-block transfer (bitblt) operation.
old-location: display\dxgk_gdirop_bitblt.htm
old-project: display
ms.assetid: f5f337dd-ab7a-4a9f-af3c-2d29dbdffe7b
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_GDIROP_BITBLT
req.alt-loc: d3dkmddi.h
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

# DXGK_GDIROP_BITBLT enumeration



## -description
<p>The DXGK_GDIROP_COLORFILL enumeration indicates the type of GDI raster operation (ROP) to implement in a GDI hardware-accelerated bit-block transfer (bitblt) operation.</p>


## -syntax

````
typedef enum _DXGK_GDIROP_BITBLT { 
  DXGK_GDIROP_INVALID    = 0,
  DXGK_GDIROP_SRCCOPY    = 1,
  DXGK_GDIROP_SRCINVERT  = 2,
  DXGK_GDIROP_SRCAND     = 3,
  DXGK_GDIROP_SRCOR      = 4,
  DXGK_GDIROP_ROP3       = 5
} DXGK_GDIROP_BITBLT;
````


## -enum-fields
<dl>

### -field DXGK_GDIROP_INVALID

<dd>
<p>Indicates that the GDI raster operation is invalid.</p>
</dd>

### -field DXGK_GDIROP_SRCCOPY

<dd>
<p>Indicates that the source rectangle is copied to the destination rectangle.</p>
</dd>

### -field DXGK_GDIROP_SRCINVERT

<dd>
<p>Indicates that the color of each pixel of the source rectangle is combined with the color of the respective pixel of the destination rectangle by using the Boolean <b>XOR</b> operator.</p>
</dd>

### -field DXGK_GDIROP_SRCAND

<dd>
<p>Indicates that the color of each pixel of the source rectangle is combined with the color of the respective pixel of the destination rectangle by using the Boolean <b>AND</b> operator.</p>
</dd>

### -field DXGK_GDIROP_SRCOR

<dd>
<p>Indicates that the color of each pixel of the source rectangle is combined with the color of the respective pixel of the destination rectangle by using the Boolean <b>OR</b> operator.</p>
</dd>

### -field DXGK_GDIROP_ROP3

<dd>
<p>Indicates that a ternary GDI raster operation (ROP3) will be applied.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 7 and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>