---
UID: NS.d3dhal._D3DHAL_DP2CREATEVERTEXSHADERDECL
title: D3DHAL_DP2CREATEVERTEXSHADERDECL
author: windows-driver-content
description: DirectX 9.0 and later versions only. The D3DHAL_DP2CREATEVERTEXSHADERDECL structure is used to create a vertex shader declaration when a D3DDP2OP_CREATEVERTEXSHADERDECL opcode is received by D3dDrawPrimitives2.
old-location: display\d3dhal_dp2createvertexshaderdecl.htm
old-project: display
ms.assetid: 063e72ef-7d57-484a-98f8-b6166a238096
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_DP2CREATEVERTEXSHADERDECL, D3DHAL_DP2CREATEVERTEXSHADERDECL
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
req.alt-api: D3DHAL_DP2CREATEVERTEXSHADERDECL
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

# D3DHAL_DP2CREATEVERTEXSHADERDECL structure



## -description
<p>
   DirectX 9.0 and later versions only.
   </p>
<p>The D3DHAL_DP2CREATEVERTEXSHADERDECL structure is used to create a vertex shader declaration when a D3DDP2OP_CREATEVERTEXSHADERDECL opcode is received by <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a>.</p>


## -syntax

````
typedef struct _D3DHAL_DP2CREATEVERTEXSHADERDECL {
  DWORD dwHandle;
  DWORD dwNumVertexElements;
} D3DHAL_DP2CREATEVERTEXSHADERDECL, *LPD3DHAL_DP2CREATEVERTEXSHADERDECL;
````


## -struct-fields
<dl>

### -field <b>dwHandle</b>

<dd>
<p>Specifies the handle to the vertex shader declaration that is assigned by the runtime. This value is guaranteed to be subzero. Flexible vertex format (FVF) codes are part of the shader declaration handle namespace. If bit zero of the handle is set, the handle passed is a shader declaration handle; otherwise, an FVF code. </p>
</dd>

### -field <b>dwNumVertexElements</b>

<dd>
<p>Specifies the number of vertex elements that make up the shader declaration. </p>
</dd>
</dl>

## -remarks
<p>When the runtime calls the driver's <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> function with this token, the driver should validate the given shader declaration and report success or failure accordingly. </p>

<p>An array of D3DVERTEXELEMENT9 structures that define the vertex elements that make up the shader declaration follow D3DHAL_DP2CREATEVERTEXSHADERDECL in the command stream. For more information about D3DVERTEXELEMENT9, see the latest DirectX SDK documentation.</p>

<p>The DirectX 9.0 runtime specifies a legacy FVF code or a declaration handle in the <b>dwHandle</b> member. The runtime indicates a declaration handle by setting bit 0 of the handle. </p>

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
<dt>D3DDP2OP_CREATEVERTEXSHADERDECL</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2vertexshader.md">D3DHAL_DP2VERTEXSHADER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2CREATEVERTEXSHADERDECL structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
