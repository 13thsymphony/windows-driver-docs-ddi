---
UID: NS:d3dkmdt._D3DKMDT_PALETTEDATA
title: "_D3DKMDT_PALETTEDATA"
author: windows-driver-content
description: The D3DKMDT_PALETTEDATA structure describes a palette entry for the display.
old-location: display\d3dkmdt_palettedata.htm
old-project: display
ms.assetid: 81ff56bb-84e5-4556-a0bf-32164b938622
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMDT_PALETTEDATA, D3DKMDT_PALETTEDATA structure [Display Devices], DmStructs_83e6b2ae-dd44-4a21-bca5-6009af1f4ced.xml, _D3DKMDT_PALETTEDATA, d3dkmdt/D3DKMDT_PALETTEDATA, display.d3dkmdt_palettedata
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
-	D3DKMDT_PALETTEDATA
product: Windows
targetos: Windows
req.typenames: D3DKMDT_PALETTEDATA
---

# _D3DKMDT_PALETTEDATA structure
The D3DKMDT_PALETTEDATA structure describes a palette entry for the display.

## Syntax
````
typedef struct _D3DKMDT_PALETTEDATA {
  BYTE Red;
  BYTE Green;
  BYTE Blue;
  BYTE Unused;
} D3DKMDT_PALETTEDATA;
````

## Members


`Red`

An 8-bit value for the red portion of the color registers.

`Green`

An 8-bit value for the green portion of the color registers.

`Blue`

An 8-bit value for the blue portion of the color registers.

`Unused`

An unused portion of the display.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkarg_setpalette.md">DXGKARG_SETPALETTE</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpalette.md">DxgkDdiSetPalette</a>