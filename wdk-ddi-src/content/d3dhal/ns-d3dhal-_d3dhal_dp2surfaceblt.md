---
UID: NS:d3dhal._D3DHAL_DP2SURFACEBLT
title: "_D3DHAL_DP2SURFACEBLT"
author: windows-driver-content
description: DirectX 9.0 and later versions only. D3DHAL_DP2SURFACEBLT is used for two dimensional system memory to video memory surface blts when D3dDrawPrimitives2 responds to the D3DDP2OP_SURFACEBLT command token.
old-location: display\d3dhal_dp2surfaceblt.htm
old-project: display
ms.assetid: 0720635c-77a2-4391-ba75-b276c0d457d5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2SURFACEBLT, D3DHAL_DP2SURFACEBLT, D3DHAL_DP2SURFACEBLT structure [Display Devices], LPD3DHAL_DP2SURFACEBLT, LPD3DHAL_DP2SURFACEBLT structure pointer [Display Devices], _D3DHAL_DP2SURFACEBLT, d3dhal/D3DHAL_DP2SURFACEBLT, d3dhal/LPD3DHAL_DP2SURFACEBLT, d3dstrct_705cb760-39d7-4953-b249-0b9a9358f0df.xml, display.d3dhal_dp2surfaceblt"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	d3dhal.h
api_name:
-	D3DHAL_DP2SURFACEBLT
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SURFACEBLT
---

# _D3DHAL_DP2SURFACEBLT structure
DirectX 9.0 and later versions only.
   

D3DHAL_DP2SURFACEBLT is used for two dimensional system memory to video memory surface blts when <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> responds to the D3DDP2OP_SURFACEBLT command token.

## Syntax
````
typedef struct _D3DHAL_DP2SURFACEBLT {
  DWORD dwSource;
  RECTL rSource;
  DWORD dwSourceMipLevel;
  DWORD dwDest;
  RECTL rDest;
  DWORD dwDestMipLevel;
  DWORD Flags;
} D3DHAL_DP2SURFACEBLT, *LPD3DHAL_DP2SURFACEBLT;
````

## Members


`dwDest`

Specifies the handle to the destination surface.

`dwDestMipLevel`

Specifies the sublevel of a MIP-map texture that is the destination for the blt.

`dwSource`

Specifies the handle to the source surface.

`dwSourceMipLevel`

Specifies the sublevel of a MIP-map texture that is the source of the blt.

`Flags`

Unused

`rDest`

Specifies a RECTL structure that specifies the upper left and lower right points of a rectangle on the destination surface. These points define the area in which the blit should occur and its position on the destination surface.

`rSource`

Specifies a RECTL structure that specifies the upper left and lower right points of a rectangle on the source surface. These points define the area of the source blit data and its position on the source surface.

## Remarks
The D3DDP2OP_SURFACEBLT operation code is identical to the D3DDP2OP_BLT operation code except that D3DDP2OP_SURFACEBLT is only used to copy system memory to video memory and is never used for stretch blts or color conversion. Because D3DDP2OP_SURFACEBLT is not used for stretch blts, no flags are currently defined.

The <b>dwSource</b> or <b>dwDest</b> member specifies the kernel handle to the top-level surface and the <b>dwSourceMipLevel</b> or <b>dwDestMiplevel</b> member specifies the sublevel for the MIP-map chain where the blt occurs.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dhal.h (include D3dhal.h) |

## See Also

D3DDP2OP_BLT



D3DDP2OP_SURFACEBLT



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SURFACEBLT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>