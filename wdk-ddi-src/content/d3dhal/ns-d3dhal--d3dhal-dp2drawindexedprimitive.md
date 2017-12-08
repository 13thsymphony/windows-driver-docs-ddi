---
UID: NS.d3dhal._D3DHAL_DP2DRAWINDEXEDPRIMITIVE
title: D3DHAL_DP2DRAWINDEXEDPRIMITIVE
author: windows-driver-content
description: DirectX 8.0 and later versions only.
old-location: display\d3dhal_dp2drawindexedprimitive.htm
old-project: display
ms.assetid: b28290c7-2c02-4422-af7b-4188d6f54b54
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_DP2DRAWINDEXEDPRIMITIVE, D3DHAL_DP2DRAWINDEXEDPRIMITIVE
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
req.alt-api: D3DHAL_DP2DRAWINDEXEDPRIMITIVE
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

# D3DHAL_DP2DRAWINDEXEDPRIMITIVE structure



## -description
<p>
   DirectX 8.0 and later versions only.
   </p>
<p>D3DHAL_DRAWINDEXEDPRIMITIVE is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_DRAWINDEXEDPRIMITIVE, and is used to render a primitive using vertex indices.</p>


## -syntax

````
typedef struct _D3DHAL_DP2DRAWINDEXEDPRIMITIVE {
  D3DPRIMITIVETYPE primType;
  INT              BaseVertexIndex;
  DWORD            MinIndex;
  DWORD            NumVertices;
  DWORD            StartIndex;
  DWORD            PrimitiveCount;
} D3DHAL_DP2DRAWINDEXEDPRIMITIVE, *LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE;
````


## -struct-fields
<dl>

### -field primType

<dd>
<p>Specifies the type of primitive to draw (one of D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP or D3DPT_TRIANGLEFAN).</p>
</dd>

### -field BaseVertexIndex

<dd>
<p>Specifies the amount that should be added to each index referenced by the various primitives to determine the actual index of the vertex elements in each vertex stream.</p>
<p>
<dl>

### -field DirectX 8.1 and earlier versions only.


### -field Specified using a DWORD.


### -field DirectX 9.0 and later versions only.


### -field Specified using an INT.

</dl>
</p>
</dd>

### -field MinIndex

<dd>
<p>Specifies the minimum index of a range of vertices that are potentially accessed by the primitives to be drawn and, therefore, which vertices should be processed.</p>
</dd>

### -field NumVertices

<dd>
<p>Specifies the number of vertices in a range that are potentially accessed by the primitives to be drawn and, therefore, which vertices should be processed.</p>
</dd>

### -field StartIndex

<dd>
<p>Specifies the first index in the index buffer from which indices are read to draw the primitives.</p>
</dd>

### -field PrimitiveCount

<dd>
<p>Specifies the number of triangles, lines or points to draw for the given primitive.</p>
</dd>
</dl>

## -remarks
<p>The vertex data can be untransformed (if the hardware supports hardware vertex processing) or transformed if the application supplied data in that form to the runtime.</p>

<p>As with vertices, the actual indices to use are not passed with the token data, but rather should be read from the currently selected index buffer. See <a href="https://msdn.microsoft.com/5bf7dc12-d988-4194-a81f-52c9c5356610">Index Buffers</a> for more details.</p>

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
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2drawindexedprimitive2.md">D3DHAL_DP2DRAWINDEXEDPRIMITIVE2</a>
</dt>
<dt>D3DDP2OP_DRAWINDEXEDPRIMITIVE</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2DRAWINDEXEDPRIMITIVE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
