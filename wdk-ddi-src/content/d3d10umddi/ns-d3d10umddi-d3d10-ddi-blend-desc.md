---
UID: NS.d3d10umddi.D3D10_DDI_BLEND_DESC
title: D3D10_DDI_BLEND_DESC
author: windows-driver-content
description: The D3D10_DDI_BLEND_DESC structure describes a blend state.
old-location: display\d3d10_ddi_blend_desc.htm
old-project: display
ms.assetid: dbb6e5ed-8d24-4b50-826b-f05f44de676a
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D10_DDI_BLEND_DESC, D3D10_DDI_BLEND_DESC
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
req.alt-api: D3D10_DDI_BLEND_DESC
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

# D3D10_DDI_BLEND_DESC structure



## -description
<p>The D3D10_DDI_BLEND_DESC structure describes a blend state.</p>


## -syntax

````
typedef struct D3D10_DDI_BLEND_DESC {
  BOOL               AlphaToCoverageEnable;
  BOOL               BlendEnable[D3D10_DDI_SIMULTANEOUS_RENDER_TARGET_COUNT];
  D3D10_DDI_BLEND    SrcBlend;
  D3D10_DDI_BLEND    DestBlend;
  D3D10_DDI_BLEND_OP BlendOp;
  D3D10_DDI_BLEND    SrcBlendAlpha;
  D3D10_DDI_BLEND    DestBlendAlpha;
  D3D10_DDI_BLEND_OP BlendOpAlpha;
  UINT8              RenderTargetWriteMask[D3D10_DDI_SIMULTANEOUS_RENDER_TARGET_COUNT];
} D3D10_DDI_BLEND_DESC;
````


## -struct-fields
<dl>

### -field AlphaToCoverageEnable

<dd>
<p>[in] A Boolean value that specifies whether transparency coverage is enabled. <b>TRUE</b> indicates transparency coverage is enabled; <b>FALSE</b> indicates transparency coverage is disabled. This member is relevant for multiple-sample antialiasing only.</p>
</dd>

### -field BlendEnable

<dd>
<p>[in] An array of Boolean values that specify whether blending is enabled for each associated render target. <b>TRUE</b> indicates blending is enabled; <b>FALSE</b> indicates blending is disabled. </p>
</dd>

### -field SrcBlend

<dd>
<p>
      [in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-blend.md">D3D10_DDI_BLEND</a>-typed value that indicates the blend mode of the source for all enabled render targets.
     </p>
</dd>

### -field DestBlend

<dd>
<p>[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-blend.md">D3D10_DDI_BLEND</a>-typed value that indicates the blend mode of the destination for all enabled render targets.</p>
</dd>

### -field BlendOp

<dd>
<p>[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-blend-op.md">D3D10_DDI_BLEND_OP</a>-typed value that indicates the blending operation for all enabled render targets.</p>
</dd>

### -field SrcBlendAlpha

<dd>
<p>[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-blend.md">D3D10_DDI_BLEND</a>-typed value that indicates the transparency blend mode of the source for all enabled render targets.</p>
</dd>

### -field DestBlendAlpha

<dd>
<p>[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-blend.md">D3D10_DDI_BLEND</a>-typed value that indicates the transparency blend mode of the destination for all enabled render targets.</p>
</dd>

### -field BlendOpAlpha

<dd>
<p>[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-blend-op.md">D3D10_DDI_BLEND_OP</a>-typed value that indicates the transparency blending operation for all enabled render targets.</p>
</dd>

### -field RenderTargetWriteMask

<dd>
<p>[in] An array of 8-bit bitwise values that indicate the write properties for each associated render target. Each bit of each element must be set to one of the following values from the D3D10_DDI_COLOR_WRITE_ENABLE enumeration.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>D3D10_DDI_COLOR_WRITE_ENABLE_RED (1)</p>
</td>
<td>
<p>Writes red</p>
</td>
</tr>
<tr>
<td>
<p>D3D10_DDI_COLOR_WRITE_ENABLE_GREEN (2)</p>
</td>
<td>
<p>Writes green</p>
</td>
</tr>
<tr>
<td>
<p>D3D10_DDI_COLOR_WRITE_ENABLE_BLUE (4)</p>
</td>
<td>
<p>Writes blue</p>
</td>
</tr>
<tr>
<td>
<p>D3D10_DDI_COLOR_WRITE_ENABLE_ALPHA (8)</p>
</td>
<td>
<p>Writes a transparency level</p>
</td>
</tr>
<tr>
<td>
<p>D3D10_DDI_COLOR_WRITE_ENABLE_ALL (1 | 2 | 4 | 8)</p>
</td>
<td>
<p>Writes red, green, blue, and a transparency level</p>
</td>
</tr>
</table>
<p> </p>
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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-calcprivateblendstatesize.md">CalcPrivateBlendStateSize</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createblendstate.md">CreateBlendState</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-blend.md">D3D10_DDI_BLEND</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-blend-op.md">D3D10_DDI_BLEND_OP</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_BLEND_DESC structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
