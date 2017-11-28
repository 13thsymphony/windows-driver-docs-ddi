---
UID: NS.d3d10umddi.D3D10DDIARG_TEX2D_RENDERTARGETVIEW
title: D3D10DDIARG_TEX2D_RENDERTARGETVIEW
author: windows-driver-content
description: The D3D10DDIARG_TEX2D_RENDERTARGETVIEW structure describes a two-dimensional (2-D) texture that is used to create a render target view in a call to the CreateRenderTargetView function.
old-location: display\d3d10ddiarg_tex2d_rendertargetview.htm
old-project: display
ms.assetid: 9537801f-568a-4fb6-b4f8-e901cf9146f6
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D10DDIARG_TEX2D_RENDERTARGETVIEW, D3D10DDIARG_TEX2D_RENDERTARGETVIEW
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D10DDIARG_TEX2D_RENDERTARGETVIEW
req.alt-loc: d3d10umddi.h
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

# D3D10DDIARG_TEX2D_RENDERTARGETVIEW structure



## -description
<p>The D3D10DDIARG_TEX2D_RENDERTARGETVIEW structure describes a two-dimensional (2-D) texture that is used to create a render target view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createrendertargetview.md">CreateRenderTargetView</a> function. </p>


## -syntax

````
typedef struct D3D10DDIARG_TEX2D_RENDERTARGETVIEW {
  UINT MipSlice;
  UINT FirstArraySlice;
  UINT ArraySize;
} D3D10DDIARG_TEX2D_RENDERTARGETVIEW;
````


## -struct-fields
<dl>

### -field <b>MipSlice</b>

<dd>
<p>[in] The identifier of the MIP-map slice. </p>
</dd>

### -field <b>FirstArraySlice</b>

<dd>
<p>[in] The identifier of the first array slice. </p>
</dd>

### -field <b>ArraySize</b>

<dd>
<p>[in] The number of array slices for the texture. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-calcprivaterendertargetviewsize.md">CalcPrivateRenderTargetViewSize</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createrendertargetview.md">CreateRenderTargetView</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541689">D3D10DDIARG_CREATERENDERTARGETVIEW</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_TEX2D_RENDERTARGETVIEW structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
