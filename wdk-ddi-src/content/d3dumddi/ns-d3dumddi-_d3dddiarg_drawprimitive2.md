---
UID: NS.D3DUMDDI._D3DDDIARG_DRAWPRIMITIVE2
title: _D3DDDIARG_DRAWPRIMITIVE2
author: windows-driver-content
description: The D3DDDIARG_DRAWPRIMITIVE2 structure describes a nonindexed primitive to draw.
old-location: display\d3dddiarg_drawprimitive2.htm
old-project: display
ms.assetid: fb9668a8-54b5-4d07-8682-af2b593308a5
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DDDIARG_DRAWPRIMITIVE2, D3DDDIARG_DRAWPRIMITIVE2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_DRAWPRIMITIVE2
req.alt-loc: d3dumddi.h
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

# _D3DDDIARG_DRAWPRIMITIVE2 structure



## -description
The D3DDDIARG_DRAWPRIMITIVE2 structure describes a nonindexed primitive to draw. 



## -syntax

````
typedef struct _D3DDDIARG_DRAWPRIMITIVE2 {
  D3DPRIMITIVETYPE PrimitiveType;
  UINT             FirstVertexOffset;
  UINT             PrimitiveCount;
} D3DDDIARG_DRAWPRIMITIVE2;
````


## -struct-fields

### -field PrimitiveType

[in] A D3DPRIMITIVETYPE-typed value that indicates the type of primitive to draw. This member can be one of the following values: D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP, or D3DPT_TRIANGLEFAN. For more information about D3DPRIMITIVETYPE, see the Microsoft Windows SDK documentation.


### -field FirstVertexOffset

[in] The offset, in bytes, in stream zero of the vertex data. This member differs from the <b>VStart</b> member of the <a href="display.d3dddiarg_drawprimitive">D3DDDIARG_DRAWPRIMITIVE</a> structure that is used with the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive.md">DrawPrimitive</a> function. In <b>VStart</b>, the start of the vertex data in the vertex stream is specified by a vertex index rather than an actual byte offset.


### -field PrimitiveCount

[in] The number of triangles, lines, or points to draw for the given primitive. 


## -remarks
The Microsoft Direct3D runtime transforms the vertex data before passing a pointer to the description of the vertex data in the <i>pData</i> parameter in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive2.md">DrawPrimitive2</a> function. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddiarg_drawprimitive">D3DDDIARG_DRAWPRIMITIVE</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive2.md">DrawPrimitive2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DRAWPRIMITIVE2 structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

