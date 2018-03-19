---
UID: NS:d3dhal._D3DHAL_DP2STARTVERTEX
title: "_D3DHAL_DP2STARTVERTEX"
author: windows-driver-content
description: A D3DHAL_DP2STARTVERTEX structure follows certain D3DHAL_DP2COMMAND structures in the command buffer, and indicates the offset in the vertex buffer for the first vertex to use in D3dDrawPrimitives2.
old-location: display\d3dhal_dp2startvertex.htm
old-project: display
ms.assetid: 302ed135-9fde-4101-876f-1f70bed501b0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2STARTVERTEX, D3DHAL_DP2STARTVERTEX, D3DHAL_DP2STARTVERTEX structure [Display Devices], LPD3DHAL_DP2STARTVERTEX, LPD3DHAL_DP2STARTVERTEX structure pointer [Display Devices], _D3DHAL_DP2STARTVERTEX, d3dhal/D3DHAL_DP2STARTVERTEX, d3dhal/LPD3DHAL_DP2STARTVERTEX, d3dstrct_1dafced6-8893-45ac-b5a2-8735fe3dbd6a.xml, display.d3dhal_dp2startvertex"
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
-	D3DHAL_DP2STARTVERTEX
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2STARTVERTEX, *LPD3DHAL_DP2STARTVERTEX
---

# _D3DHAL_DP2STARTVERTEX structure
A D3DHAL_DP2STARTVERTEX structure follows certain <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structures in the command buffer, and indicates the offset in the vertex buffer for the first vertex to use in <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.

## Syntax
````
typedef struct _D3DHAL_DP2STARTVERTEX {
  WORD wVStart;
} D3DHAL_DP2STARTVERTEX, *LPD3DHAL_DP2STARTVERTEX;
````

## Members


`wVStart`

Specifies an additional offset to be added to any index used for determining the location of vertices in the vertex buffer (in the case of indexed primitives).

## Remarks
A D3DHAL_DP2STARTVERTEX structure follows a D3DHAL_DP2COMMAND structure in the command buffer when the <b>bCommand</b> member of D3DHAL_DP2COMMAND is one of the following values:

<ul>
<li>
D3DDP2OP_INDEXEDLINELIST2

</li>
<li>
D3DDP2OP_INDEXEDLINESTRIP

</li>
<li>
D3DDP2OP_INDEXEDTRIANGLELIST2

</li>
<li>
D3DDP2OP_INDEXEDTRIANGLESTRIP

</li>
<li>
D3DDP2OP_INDEXEDTRIANGLEFAN

</li>
</ul>
The first vertex of such primitives is located (<b>wVStart</b> + <b>dwVertexOffset</b>) bytes from the beginning of the vertex buffer, where <b>dwVertexOffset</b> is a member of <a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dhal.h (include D3dhal.h) |

## See Also

D3DDP2OP_INDEXEDTRIANGLESTRIP



D3DDP2OP_INDEXEDTRIANGLEFAN



<a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a>



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



D3DDP2OP_INDEXEDLINELIST2



D3DDP2OP_INDEXEDTRIANGLELIST2



D3DDP2OP_INDEXEDLINESTRIP



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>