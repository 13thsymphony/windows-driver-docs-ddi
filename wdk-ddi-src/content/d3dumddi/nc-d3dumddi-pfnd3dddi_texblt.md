---
UID: NC:d3dumddi.PFND3DDDI_TEXBLT
title: PFND3DDDI_TEXBLT
author: windows-driver-content
description: The TexBlt function performs a bit-block transfer (bitblt) operation from a source texture to a destination texture, including all of the sublevels of the source texture.
old-location: display\texblt.htm
old-project: display
ms.assetid: 1ddfd822-7a43-4976-a153-ba862d6dfd82
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_TEXBLT, TexBlt, TexBlt callback function [Display Devices], UserModeDisplayDriver_Functions_1d3c2c6d-849d-46c2-9934-f3c4e5720edf.xml, d3dumddi/TexBlt, display.texblt
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
-	TexBlt
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_TEXBLT callback function
The <i>TexBlt</i> function performs a bit-block transfer (bitblt) operation from a source texture to a destination texture, including all of the sublevels of the source texture.

## Syntax

```
PFND3DDDI_TEXBLT Pfnd3dddiTexblt;

HRESULT Pfnd3dddiTexblt(
  HANDLE hDevice,
  CONST D3DDDIARG_TEXBLT *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>TexBlt</i> returns S_OK or an appropriate error result if the texture bitblt operation is not successfully performed.

## Remarks

The Microsoft Direct3D runtime calls the user-mode display driver's <i>TexBlt</i> function to inform the driver to perform a bitblt operation from a source texture to a destination texture. A texture can also be a cubic environment map. The driver should copy the rectangle that is specified by the <b>SrcRect</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543384">D3DDDIARG_TEXBLT</a> structure in the source texture to the location that is specified by the <b>DstPoint</b> member of D3DDDIARG_TEXBLT in the destination texture. The destination and source textures are identified by the <b>hDstResource</b> and <b>hSrcResource</b> handles of D3DDDIARG_TEXBLT, respectively. 

For MIP-mapped textures, the driver must also copy all of the MIP-map sublevels that are present in the source texture. The source and destination textures might possibly contain different numbers of MIP-map levels. In this situation, the driver should copy the common levels. For example, if a 256x256 source texture has eight MIP-map levels, and if the destination is a 64x64 texture with six levels, the driver should copy the six corresponding levels from the source. Note that the dimensions of the top MIP level of the destination texture is always less than or equal to the dimensions of the top MIP level of the source texture.

The source and destination handles always refer to the top-level surfaces and never to any MIP-map sublevel. 

To copy an arbitrary level of a MIP-map texture, the runtime calls the driver's <a href="https://msdn.microsoft.com/e87576c6-0173-4d8e-bbaf-b82e2907140a">Blt</a> function instead.

The pixel formats of the source and destination textures are identical and, in general, the specified bitblt operation is safe to perform.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/e87576c6-0173-4d8e-bbaf-b82e2907140a">Blt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543384">D3DDDIARG_TEXBLT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>