---
UID: NS.d3dhal._D3DHAL_DP2TRIANGLEFAN_IMM
title: D3DHAL_DP2TRIANGLEFAN_IMM
author: windows-driver-content
description: One D3DHAL_DP2TRIANGLEFAN_IMM structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_TRIANGLEFAN_IMM, and is used to render a triangle fan.
old-location: display\d3dhal_dp2trianglefan_imm.htm
old-project: display
ms.assetid: a2f6f184-1178-4578-aafa-0bd088d42634
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_DP2TRIANGLEFAN_IMM, D3DHAL_DP2TRIANGLEFAN_IMM
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
req.alt-api: D3DHAL_DP2TRIANGLEFAN_IMM
req.alt-loc: d3dhal.h
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
req.iface: 
---

# D3DHAL_DP2TRIANGLEFAN_IMM structure



## -description
<p>One D3DHAL_DP2TRIANGLEFAN_IMM structure is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_TRIANGLEFAN_IMM, and is used to render a triangle fan.</p>


## -syntax

````
typedef struct _D3DHAL_DP2TRIANGLEFAN_IMM {
  DWORD dwEdgeFlags;
} D3DHAL_DP2TRIANGLEFAN_IMM, *LPD3DHAL_DP2TRIANGLEFAN_IMM;
````


## -struct-fields
<dl>

### -field dwEdgeFlags

<dd>
<p>Specifies a bitmask that identifies which of the fan's outside edges should be rendered when the fill mode is D3DFILL_WIREFRAME. A set bit indicates that its corresponding edge should be rendered. For more information about this bitmask, see the Remarks section.</p>
</dd>
</dl>

## -remarks
<p>One D3DHAL_DP2TRIANGLEFAN_IMM structure immediately follows the D3DHAL_DP2COMMAND structure in the command buffer. The triangle fan's vertex data is DWORD-aligned immediately following the D3DHAL_DP2TRIANGLEFAN_IMM structure in the command buffer.</p>

<p>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> should process a total of <b>wPrimitiveCount</b>+2 vertices from the command buffer, three vertices per triangle, rendering <b>wPrimitiveCount</b> triangles. The sequence of triangles rendered is (<b>V[</b>1<b>]</b>, <b>V[</b>2<b>]</b>, <b>V[</b>0<b>]</b>), (<b>V[</b>2<b>]</b>, <b>V[</b>3<b>]</b>, <b>V[</b>0<b>]</b>), (<b>V[</b>3<b>]</b>, <b>V[</b>4<b>]</b>, <b>V[</b>0<b>]</b>), ..., (<b>V[wPrimitiveCount]</b>, <b>V[wPrimitiveCount]</b> + 1<b>]</b>, <b>V[</b>0<b>]</b>). The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.</p>

<p>The driver must check the edge flag for each of the fan's outside edges when the fill mode is D3DFILL_WIREFRAME. Starting from the least significant bit of <b>dwEdgeFlags</b>, bit 0 applies to the <b>V[</b>0<b>]</b>-<b>V[</b>1<b>]</b> edge, bit 1 applies to the <b>V[</b>1<b>]</b>-<b>V[</b>2<b>]</b> edge, ..., bit <b>wPrimitiveCount</b> applies to the <b>V[wPrimitiveCount]</b>-<b>V[[wPrimitiveCount]</b>+1<b>]</b> edge, and bit (<b>wPrimitiveCount</b> + 1) applies to the <b>V[[wPrimitiveCount]</b>+1<b>]</b>-<b>V[</b>0<b>]</b> edge.</p>

<p>The following figure shows a portion of a sample command buffer containing a D3DDP2OP_TRIANGLEFAN_IMM command, a D3DHAL_DP2TRIANGLEFAN_IMM structure, and the vertex data. The driver should process the five vertices from the command buffer, rendering a fan with three triangles defined by (v[1], v[2], v[0]), (v[2], v[3], v[0]), (v[3], v[4], v[0]).</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dhal.h (include D3dhal.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>D3DDP2OP_TRIANGLEFAN_IMM</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2TRIANGLEFAN_IMM structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
