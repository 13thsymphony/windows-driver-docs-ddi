---
UID: NS.d3dhal._D3DHAL_DP2LINELIST
title: D3DHAL_DP2LINELIST
author: windows-driver-content
description: One D3DHAL_DP2LINELIST structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_LINELIST, and is used to render unconnected line segments.
old-location: display\d3dhal_dp2linelist.htm
old-project: display
ms.assetid: ac8346e9-46ce-4205-a46b-c327888b952d
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_DP2LINELIST, D3DHAL_DP2LINELIST, *LPD3DHAL_DP2LINELIST
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
req.alt-api: D3DHAL_DP2LINELIST
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

# D3DHAL_DP2LINELIST structure



## -description
<p>One D3DHAL_DP2LINELIST structure is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_LINELIST, and is used to render unconnected line segments.</p>


## -syntax

````
typedef struct _D3DHAL_DP2LINELIST {
  WORD wVStart;
} D3DHAL_DP2LINELIST, *LPD3DHAL_DP2LINELIST;
````


## -struct-fields
<dl>

### -field <b>wVStart</b>

<dd>
<p>Specifies the index into the vertex buffer containing coordinate data for the initial vertex of the line list.</p>
</dd>
</dl>

## -remarks
<p>One D3DHAL_DP2LINELIST structure follows the D3DHAL_DP2COMMAND structure in the command buffer.</p>

<p>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> should sequentially process a total of <b>wPrimitiveCount</b> * 2 vertices from the vertex buffer, two vertices per line, rendering a total of <b>wPrimitiveCount</b> lines. Starting from the vertex buffer offset, the sequence of lines rendered is (<b>wVStart</b>, <b>wVStart</b> + 1), (<b>wVStart</b> + 2, <b>wVStart</b> + 3),..., (<b>wVStart</b> + (<b>wPrimitiveCount</b> -1 ) * 2, <b>wVStart</b> + (<b>wPrimitiveCount</b> * 2 - 1)). The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.</p>

<p>The following figure shows a portion of a sample command buffer containing a D3DDP2OP_LINELIST command and one D3DHAL_DP2LINELIST structure. The driver should draw three lines using the following six vertices from the vertex buffer: (v[0], v[1]), (v[2], v[3]), (v[4], v[5]).</p>

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
<dt>D3DDP2OP_LINELIST</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2LINELIST structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
