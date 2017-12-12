---
UID: NS.D3DHAL._D3DHAL_DP2TRIANGLEFAN
title: _D3DHAL_DP2TRIANGLEFAN
author: windows-driver-content
description: One D3DHAL_DP2TRIANGLEFAN structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_TRIANGLEFAN, and is used to render a triangle fan.
old-location: display\d3dhal_dp2trianglefan.htm
old-project: display
ms.assetid: 563fe6c9-868e-4b84-b14b-baee8ab00a2d
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DHAL_DP2TRIANGLEFAN, D3DHAL_DP2TRIANGLEFAN, *LPD3DHAL_DP2TRIANGLEFAN
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
req.alt-api: D3DHAL_DP2TRIANGLEFAN
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
---

# _D3DHAL_DP2TRIANGLEFAN structure



## -description
One D3DHAL_DP2TRIANGLEFAN structure is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="display.d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_TRIANGLEFAN, and is used to render a triangle fan.



## -syntax

````
typedef struct _D3DHAL_DP2TRIANGLEFAN {
  WORD wVStart;
} D3DHAL_DP2TRIANGLEFAN, *LPD3DHAL_DP2TRIANGLEFAN;
````


## -struct-fields

### -field wVStart

Specifies the index into the vertex buffer containing coordinate data for the initial vertex of the triangle fan.


## -remarks
One D3DHAL_DP2TRIANGLEFAN structure follows the D3DHAL_DP2COMMAND structure in the command buffer.


<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> should process a total of <b>wPrimitiveCount</b> + 2 vertices from the vertex buffer, three vertices per triangle, rendering <b>wPrimitiveCount</b> triangles. Starting from the vertex buffer offset, the sequence of triangles rendered is (<b>wVStart </b> + 1, <b>wVStart </b> + 2, <b>wVStart </b>), (<b>wVStart </b> + 2, <b>wVStart </b> + 3, <b>wVStart </b>),..., (<b>wVStart </b> + <b>wPrimitiveCount</b>, <b>wVStart </b>+<b>wPrimitiveCount</b> + 1, <b>wVStart </b>). The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_TRIANGLEFAN command and a D3DHAL_DP2TRIANGLEFAN structure. The driver should process six vertices from the vertex buffer, rendering a fan with four triangles defined by (v[3], v[4], v[2]), (v[4], v[5], v[2]), (v[5], v[6], v[2]), (v[6], v[7], v[2]).


## -requirements
<table>
<tr>
<th width="30%">
Header

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
<dt>D3DDP2OP_TRIANGLEFAN</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="display.d3dhal_dp2command">D3DHAL_DP2COMMAND</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2TRIANGLEFAN structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

