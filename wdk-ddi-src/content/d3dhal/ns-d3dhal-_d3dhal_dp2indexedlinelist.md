---
UID : NS:d3dhal._D3DHAL_DP2INDEXEDLINELIST
title : _D3DHAL_DP2INDEXEDLINELIST
author : windows-driver-content
description : D3DHAL_DP2INDEXEDLINELIST is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDLINELIST, and is used to render the lines using vertex indices.
old-location : display\d3dhal_dp2indexedlinelist.htm
old-project : display
ms.assetid : 6205df9f-a6b1-4dd1-97a8-5d0d57a7ddd1
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DHAL_DP2INDEXEDLINELIST, D3DHAL_DP2INDEXEDLINELIST, *LPD3DHAL_DP2INDEXEDLINELIST
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dhal.h
req.include-header : D3dhal.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DHAL_DP2INDEXEDLINELIST
req.alt-loc : d3dhal.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : D3DHAL_DP2INDEXEDLINELIST, *LPD3DHAL_DP2INDEXEDLINELIST
---

# _D3DHAL_DP2INDEXEDLINELIST structure
D3DHAL_DP2INDEXEDLINELIST is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_INDEXEDLINELIST, and is used to render the lines using vertex indices.

## Syntax
````
typedef struct _D3DHAL_DP2INDEXEDLINELIST {
  WORD wV1;
  WORD wV2;
} D3DHAL_DP2INDEXEDLINELIST, *LPD3DHAL_DP2INDEXEDLINELIST;
````

## Members

        
            `wV1`

            Specifies the index into the vertex buffer, identifying the first endpoint of the line.
        
            `wV2`

            Specifies the index into the vertex buffer, identifying the second endpoint of the line.

    ## Remarks
        <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> should process (<b>wPrimitiveCount</b> * 2) indexes from the command buffer, in effect processing <b>wPrimitiveCount</b> D3DHAL_DP2INDEXEDLINELIST structures. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

The driver should process a total of (<b>wPrimitiveCount</b> * 2) vertices from the vertex buffer, two vertices per line. The sequence of lines rendered is (<b>wV1</b>₀, <b>wV2</b>₀), (<b>wV1</b>₁, <b>wV2</b>₁), ..., (<b>wV1</b>ₙ,<b>wV2</b>ₙ), where n equals (<b>wPrimitiveCount</b>- 1). The driver should interpret the vertex buffer indexes based on the current command as follows:

When the command is D3DDP2OP_INDEXEDLINELIST, the vertex buffer indexes are relative to the vertex buffer offset specified by the <b>dwVertexOffset</b> member of the <a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a> structure.

When the command is D3DDP2OP_INDEXEDLINELIST2, a <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2startvertex.md">D3DHAL_DP2STARTVERTEX</a> structure immediately follows it and precedes the D3DHAL_DP2INDEXEDLINELIST structure(s) in the command buffer. The vertex buffer indexes are relative to the vertex buffer offset specified by <b>dwVertexOffset</b> plus the base offset obtained from the <b>wVStart</b> member of the D3DHAL_DP2STARTVERTEX structure.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_INDEXEDLINELIST command and two D3DHAL_DP2INDEXEDLINELIST structures. The driver should draw two lines using the following four vertices from the vertex buffer: (v[0], v[4]), (v[5], v[6]).

Similarly, the following figure shows a portion of a sample command buffer containing a D3DDP2OP_INDEXEDLINELIST2 command, a D3DHAL_DP2STARTVERTEX offset, and two D3DHAL_DP2INDEXEDLINELIST structures. The driver should process four vertices from the vertex buffer, rendering two lines defined by (v[3], v[7]), (v[8], v[9]).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dhal.h (include D3dhal.h) |

    ## See Also

        <dl>
<dt>D3DDP2OP_INDEXEDLINELIST</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2startvertex.md">D3DHAL_DP2STARTVERTEX</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2INDEXEDLINELIST structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>