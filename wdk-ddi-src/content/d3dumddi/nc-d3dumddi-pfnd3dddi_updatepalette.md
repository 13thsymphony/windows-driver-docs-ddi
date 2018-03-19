---
UID: NC:d3dumddi.PFND3DDDI_UPDATEPALETTE
title: PFND3DDDI_UPDATEPALETTE
author: windows-driver-content
description: The UpdatePalette function updates a texture palette.
old-location: display\updatepalette.htm
old-project: display
ms.assetid: 7c22e0c9-cc24-4398-88b7-c91855cbc731
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_UPDATEPALETTE, UpdatePalette, UpdatePalette callback function [Display Devices], UserModeDisplayDriver_Functions_d3b21e65-68dc-44d9-b5b3-96f37588965e.xml, d3dumddi/UpdatePalette, display.updatepalette
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	UpdatePalette
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_UPDATEPALETTE callback function
The <i>UpdatePalette</i> function updates a texture palette.

## Syntax

```
PFND3DDDI_UPDATEPALETTE Pfnd3dddiUpdatepalette;

HRESULT Pfnd3dddiUpdatepalette(
  HANDLE hDevice,
  CONST D3DDDIARG_UPDATEPALETTE *,
  CONST PALETTEENTRY *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`



`*`




## Return Value

<i>UpdatePalette</i> returns S_OK or an appropriate error result if the texture palette is not successfully updated.

## Remarks

The palette data in the array that is specified by <i>pPaletteData</i> consists of one UINT value for each palette entry (PALETTEENTRY structure). The palette entry is in ARGB format, with 8 bits for each of the four channels.

The user-mode display driver uses the following members of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_updatepalette.md">D3DDDIARG_UPDATEPALETTE</a> structure that is pointed to by <i>pData</i> to update the texture palette: 

<ul>
<li>
The <b>PaletteHandle</b> member specifies the handle to the palette that is associated with the surface.

</li>
<li>
The <b>StartIndex</b> member specifies the index of the entry in the array at <i>pPaletteData</i> where the update should start.

</li>
<li>
The <b>NumEntries</b> member specifies the number of entries in the array at <i>pPaletteData</i> to update.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_updatepalette.md">D3DDDIARG_UPDATEPALETTE</a>