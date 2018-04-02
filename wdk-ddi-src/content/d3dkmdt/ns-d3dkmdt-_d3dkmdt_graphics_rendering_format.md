---
UID: NS:d3dkmdt._D3DKMDT_GRAPHICS_RENDERING_FORMAT
title: "_D3DKMDT_GRAPHICS_RENDERING_FORMAT"
author: windows-driver-content
description: The D3DKMDT_GRAPHICS_RENDERING_FORMAT structure contains information about a primary rendering surface.
old-location: display\d3dkmdt_graphics_rendering_format.htm
old-project: display
ms.assetid: 954cc3f6-731f-4c55-bf61-63b5d48248c0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMDT_GRAPHICS_RENDERING_FORMAT, D3DKMDT_GRAPHICS_RENDERING_FORMAT structure [Display Devices], DmStructs_c51e5886-bbd0-48a2-8be7-98d10b13fc2d.xml, _D3DKMDT_GRAPHICS_RENDERING_FORMAT, d3dkmdt/D3DKMDT_GRAPHICS_RENDERING_FORMAT, display.d3dkmdt_graphics_rendering_format
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	D3DKMDT_GRAPHICS_RENDERING_FORMAT
product: Windows
targetos: Windows
req.typenames: D3DKMDT_GRAPHICS_RENDERING_FORMAT
---

# _D3DKMDT_GRAPHICS_RENDERING_FORMAT structure
The D3DKMDT_GRAPHICS_RENDERING_FORMAT structure contains information about a primary rendering surface.

## Syntax
```
typedef struct _D3DKMDT_GRAPHICS_RENDERING_FORMAT {
  D3DKMDT_2DREGION                PrimSurfSize;
  D3DKMDT_2DREGION                VisibleRegionSize;
  DWORD                           Stride;
  D3DDDIFORMAT                    PixelFormat;
  D3DKMDT_COLOR_BASIS             ColorBasis;
  D3DKMDT_PIXEL_VALUE_ACCESS_MODE PixelValueAccessMode;
} D3DKMDT_GRAPHICS_RENDERING_FORMAT;
```

## Members


`PrimSurfSize`

A D3DKMDT_2DREGION structure that holds the size (number of pixels, both horizontal and vertical) of the surface.

`VisibleRegionSize`

A D3DKMDT_2DREGION structure that holds the size of the visible portion of the surface.

`Stride`

The offset, in bytes, between one scan line and the next scan line in the surface.

`PixelFormat`

A value from the D3DDDIFORMAT enumeration that indicates the pixel format of the surface.

`ColorBasis`

A value from the D3DKMDT_COLOR_BASIS enumeration that indicates the color basis used to encode the content of the surface.

`PixelValueAccessMode`

A value from the D3DKMDT_PIXEL_VALUE_ACCESS_MODE enumeration that indicates the type of data (for example, direct color values or palette indexes) that are stored in the surface.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>