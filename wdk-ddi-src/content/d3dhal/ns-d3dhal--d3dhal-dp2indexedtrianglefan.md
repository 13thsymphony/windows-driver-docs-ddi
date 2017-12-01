---
UID: NS.d3dhal._D3DHAL_DP2INDEXEDTRIANGLEFAN
title: D3DHAL_DP2INDEXEDTRIANGLEFAN
author: windows-driver-content
description: D3DHAL_DP2INDEXEDTRIANGLEFAN is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDTRIANGLEFAN, and is used to render a sequence of connected triangles using vertex indices. All of the triangles share a common vertex.
old-location: display\d3dhal_dp2indexedtrianglefan.htm
old-project: display
ms.assetid: cdc3dd16-6bf2-495c-8df1-aa9c670d1e7a
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_DP2INDEXEDTRIANGLEFAN, D3DHAL_DP2INDEXEDTRIANGLEFAN, *LPD3DHAL_DP2INDEXEDTRIANGLEFAN
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
req.alt-api: D3DHAL_DP2INDEXEDTRIANGLEFAN
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

# D3DHAL_DP2INDEXEDTRIANGLEFAN structure



## -description
<p>D3DHAL_DP2INDEXEDTRIANGLEFAN is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_INDEXEDTRIANGLEFAN, and is used to render a sequence of connected triangles using vertex indices. All of the triangles share a common vertex.</p>


## -syntax

````
typedef struct _D3DHAL_DP2INDEXEDTRIANGLEFAN {
  WORD wV[3];
} D3DHAL_DP2INDEXEDTRIANGLEFAN, *LPD3DHAL_DP2INDEXEDTRIANGLEFAN;
````


## -struct-fields
<dl>

### -field <b>wV</b>

<dd>
<p>Specifies the indexes into the vertex buffer from which the driver obtains coordinate data for the vertices making up the triangle fan. </p>
<p>Although this member has only enough space to contain three indexes, this array of indexes should be treated as a variable-sized array with (<b>wPrimitiveCount</b> + 2) elements. (<b>wPrimitiveCount</b> is a member of the D3DHAL_DP2COMMAND structure.)</p>
</dd>
</dl>

## -remarks
<p>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> should process (<b>wPrimitiveCount</b>+2) indexes from the command buffer, in effect, processing <b>wPrimitiveCount</b> D3DHAL_DP2INDEXEDTRIANGLEFAN structures. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.</p>

<p>The driver should process a total of (<b>wPrimitiveCount</b> + 2) vertices from the vertex buffer, three vertices per triangle. The sequence of triangles rendered is: (<b>wV[</b>1<b>]</b>, <b>wV[</b>2<b>]</b>, <b>wV[</b>0<b>]</b>), (<b>wV[</b>2<b>]</b>, <b>wV[</b>3<b>]</b>, <b>wV[</b>0<b>]</b>), (<b>wV[</b>3<b>]</b>, <b>wV[</b>4<b>]</b>, <b>wV[</b>0<b>]</b>), ..., (<b>wV[wPrimitiveCount]</b>, <b>wV[wPrimitiveCount]</b>+1<b>]</b>, <b>wV[</b>0<b>]</b>). Notice that all of the triangles have the vertex specified in <b>wV[</b>0<b>]</b>in common.</p>

<p>A <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2startvertex.md">D3DHAL_DP2STARTVERTEX</a> structure immediately follows the command in the command buffer. The vertex buffer indexes are relative to the vertex buffer offset specified by the <b>dwVertexOffset</b> member of the <a href="..\d3dhal\ns-d3dhal--d3dhal-drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a> structure plus the base offset obtained from the <b>wVStart</b> member of the D3DHAL_DP2STARTVERTEX structure.</p>

<p>The following figure shows a portion of a sample command buffer containing a D3DDP2OP_INDEXEDTRIANGLEFAN command, a D3DHAL_DP2STARTVERTEX offset, and a logical list of D3DHAL_DP2INDEXEDTRIANGLEFAN structures. The driver should process five vertices from the vertex buffer, rendering a fan with three triangles defined by (v[4], v[5], v[7]), (v[5], v[6], v[7]), (v[6], v[9], v[7]).</p>

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
<dt>D3DDP2OP_INDEXEDTRIANGLEFAN</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2startvertex.md">D3DHAL_DP2STARTVERTEX</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2INDEXEDTRIANGLEFAN structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
