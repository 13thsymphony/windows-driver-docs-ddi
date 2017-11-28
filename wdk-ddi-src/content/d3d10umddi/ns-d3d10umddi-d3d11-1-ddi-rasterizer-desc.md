---
UID: NS.d3d10umddi.D3D11_1_DDI_RASTERIZER_DESC
title: D3D11_1_DDI_RASTERIZER_DESC
author: windows-driver-content
description: Describes a rasterizer state. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\d3d11_1_ddi_rasterizer_desc.htm
old-project: display
ms.assetid: a78655b3-3ca3-4632-9ac4-3efae6b10a0c
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D11_1_DDI_RASTERIZER_DESC, D3D11_1_DDI_RASTERIZER_DESC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1_DDI_RASTERIZER_DESC
req.alt-loc: D3d10umddi.h
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

# D3D11_1_DDI_RASTERIZER_DESC structure



## -description
<p>Describes a rasterizer state. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.</p>


## -syntax

````
typedef struct D3D11_1_DDI_RASTERIZER_DESC {
  D3D10_DDI_FILL_MODE FillMode;
  D3D10_DDI_CULL_MODE CullMode;
  BOOL                FrontCounterClockwise;
  INT32               DepthBias;
  FLOAT               DepthBiasClamp;
  FLOAT               SlopeScaledDepthBias;
  BOOL                DepthClipEnable;
  BOOL                ScissorEnable;
  BOOL                MultisampleEnable;
  BOOL                AntialiasedLineEnable;
  UINT                ForcedSampleCount;
} D3D11_1_DDI_RASTERIZER_DESC;
````


## -struct-fields
<dl>

### -field <b>FillMode</b>

<dd>
<p>[in] A value that specifies the fill mode for primitives. This member must be set to one of the following values from the D3D10_DDI_FILL_MODE enumeration.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>D3D10_DDI_FILL_WIREFRAME (2)</p>
</td>
<td>
<p>Fills wireframes.</p>
</td>
</tr>
<tr>
<td>
<p>D3D10_DDI_FILL_SOLID (3)</p>
</td>
<td>
<p>Fills solids.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>CullMode</b>

<dd>
<p>[in] A value that specifies how back-facing triangles are culled, if at all. This member must be set to one of the following values from the D3D10_DDI_CULL_MODE enumeration.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>D3D10_DDI_CULL_NONE (1)</p>
</td>
<td>
<p>Do not cull any triangles.</p>
</td>
</tr>
<tr>
<td>
<p>D3D10_DDI_CULL_FRONT (2)</p>
</td>
<td>
<p>Cull front faces.</p>
</td>
</tr>
<tr>
<td>
<p>D3D10_DDI_CULL_BACK (3)</p>
</td>
<td>
<p>Cull back faces.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>FrontCounterClockwise</b>

<dd>
<p>[in] A Boolean value that specifies whether vertices that are provided in a counter-clockwise order (with respect to the rasterizer) are front facing. <b>TRUE</b> indicates they are; <b>FALSE</b> indicates that counter-clockwise vertices indicate back facing. </p>
</dd>

### -field <b>DepthBias</b>

<dd>
<p>[in] A depth-bias constant to use in biasing formulas. For more information about <b>DepthBias</b>, see the Remarks section. </p>
</dd>

### -field <b>DepthBiasClamp</b>

<dd>
<p>[in] A single-precision float vector that is used in biasing formulas. For more information about <b>DepthBiasClamp</b>, see the Remarks section. </p>
</dd>

### -field <b>SlopeScaledDepthBias</b>

<dd>
<p>[in] A single-precision float vector that is used in biasing formulas. For more information about <b>SlopeScaledDepthBias</b>, see the Remarks section. </p>
</dd>

### -field <b>DepthClipEnable</b>

<dd>
<p>[in] A Boolean value that specifies whether the driver should clip vertex z coordinates against the viewport depth range. <b>TRUE</b> indicates to clip; <b>FALSE</b> indicates not to clip. </p>
</dd>

### -field <b>ScissorEnable</b>

<dd>
<p>[in] A Boolean value that specifies whether the driver should discard pixels that fall outside the appropriate scissor rectangular area. <b>TRUE</b> indicates to discard; <b>FALSE</b> indicates not to discard. </p>
</dd>

### -field <b>MultisampleEnable</b>

<dd>
<p>[in] A Boolean value that specifies whether the driver must follow multiple-sampled rasterization rules. <b>TRUE</b> indicates to follow the rules; <b>FALSE</b> indicates following the rules is not required. Multiple-sampled rasterization rules hold true even if render targets contain only a single sample.  </p>
</dd>

### -field <b>AntialiasedLineEnable</b>

<dd>
<p>[in] A Boolean value that specifies whether the driver should render lines that follow the antialiased line rasterization rules. <b>TRUE</b> indicates to follow the rules; <b>FALSE</b> indicates following the rules is not required. The driver ignores the value in <b>AntialiasedLineEnable</b> if multiple-sampling rasterization rules are used instead. </p>
</dd>

### -field <b>ForcedSampleCount</b>

<dd>
<p>[in] During rendering of unordered access vews (UAVs) or rendering target views (RTVs), specifies whether to force a sample count, and if so, the maximum sample count. Valid values are 0, 1, 4, 8, and 16.</p>
<p>If zero, the driver should not force a sample count.</p>
</dd>
</dl>

## -remarks
<p>One of the artifacts with shadow buffer-based shadows is "shadow acne" (that is, a surface that shadows itself in an intermittent way because of inexactness in computing the depth of the surface from the shader that is compared against the depth of the same surface in the shadow buffer). One way to alleviate shadow acne is to use the <b>DepthBias</b> and <b>SlopeScaledDepthBias</b> members when you render a shadow buffer. The intent is to push surfaces out enough when rendering a shadow buffer. When those surfaces are compared against themselves through shader-computed z during the shadow test, the comparison result is consistent across the surface, and local-self-shadowing is avoided.</p>

<p>However, using <b>DepthBias</b> and <b>SlopeScaledDepthBias</b> alone can introduce a few artifacts. For example, an extremely steep polygon causes the bias equation to explode, which pushes the polygon extremely far away from the originating surface in the shadow map. Consider a steep face, with respect to a light, that is pushed away extremely far in relation to the dimensions of the parent object by depth biasing. Suppose this face is surrounded by shallower faces that the bias equation pushed out much less. The resulting shadow map has a huge discontinuity that can cause holes in the shadow that is cast by one surface onto another surface closer than the exploded faces. One way to help alleviate this particular problem is to use the <b>DepthBiasClamp</b> member, which provides an application-settable upper bound (positive or negative) on the magnitude of z biasing.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
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