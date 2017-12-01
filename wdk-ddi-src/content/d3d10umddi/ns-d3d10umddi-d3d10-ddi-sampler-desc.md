---
UID: NS.d3d10umddi.D3D10_DDI_SAMPLER_DESC
title: D3D10_DDI_SAMPLER_DESC
author: windows-driver-content
description: The D3D10_DDI_SAMPLER_DESC structure describes a sampler.
old-location: display\d3d10_ddi_sampler_desc.htm
old-project: display
ms.assetid: 2f65b381-bf81-45b5-9583-793e4ffb453c
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D10_DDI_SAMPLER_DESC, D3D10_DDI_SAMPLER_DESC
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
req.alt-api: D3D10_DDI_SAMPLER_DESC
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

# D3D10_DDI_SAMPLER_DESC structure



## -description
<p>The D3D10_DDI_SAMPLER_DESC structure describes a sampler.</p>


## -syntax

````
typedef struct D3D10_DDI_SAMPLER_DESC {
  D3D10_DDI_FILTER               Filter;
  D3D10_DDI_TEXTURE_ADDRESS_MODE AddressU;
  D3D10_DDI_TEXTURE_ADDRESS_MODE AddressV;
  D3D10_DDI_TEXTURE_ADDRESS_MODE AddressW;
  FLOAT                          MipLODBias;
  UINT                           MaxAnisotropy;
  D3D10_DDI_COMPARISON_FUNC      ComparisonFunc;
  FLOAT                          BorderColor[4];
  FLOAT                          MinLOD;
  FLOAT                          MaxLOD;
} D3D10_DDI_SAMPLER_DESC;
````


## -struct-fields
<dl>

### -field <b>Filter</b>

<dd>
<p>[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-filter.md">D3D10_DDI_FILTER</a>-typed value that indicates the filter property for a sampler. </p>
</dd>

### -field <b>AddressU</b>

<dd>
<p>[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-texture-address-mode.md">D3D10_DDI_TEXTURE_ADDRESS_MODE</a>-typed value that indicates the texture-address mode for the u coordinate.</p>
</dd>

### -field <b>AddressV</b>

<dd>
<p>[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-texture-address-mode.md">D3D10_DDI_TEXTURE_ADDRESS_MODE</a>-typed value that indicates the texture-address mode for the v coordinate.</p>
</dd>

### -field <b>AddressW</b>

<dd>
<p>[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-texture-address-mode.md">D3D10_DDI_TEXTURE_ADDRESS_MODE</a>-typed value that indicates the texture-address mode for the w coordinate.</p>
</dd>

### -field <b>MipLODBias</b>

<dd>
<p>[in] A single-precision float that affects the level that the driver selects for MIP-map level of detail (LOD). </p>
</dd>

### -field <b>MaxAnisotropy</b>

<dd>
<p>[in] The maximum valid value for the anisotropy texture-stage state. </p>
</dd>

### -field <b>ComparisonFunc</b>

<dd>
<p>[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-comparison-func.md">D3D10_DDI_COMPARISON_FUNC</a>-typed value that indicates the sampler-comparison function to perform.</p>
</dd>

### -field <b>BorderColor</b>

<dd>
<p>[in] A four-element array of single-precision float vectors for RGBA, where Red == 0. The border color is used when the D3D10_DDI_TEXTURE_ADDRESS_BORDER value is specified in the <b>AddressU</b>, <b>AddressV</b>, or <b>AddressW</b> member. The float should be converted to the appropriate resource format. </p>
</dd>

### -field <b>MinLOD</b>

<dd>
<p>[in] A single-precision float vector for the minimum level of detail (LOD) for the sampler. </p>
</dd>

### -field <b>MaxLOD</b>

<dd>
<p>[in] A single-precision float vector for the maximum level of detail (LOD) for the sampler. </p>
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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-calcprivatesamplersize.md">CalcPrivateSamplerSize</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createsampler.md">CreateSampler</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-comparison-func.md">D3D10_DDI_COMPARISON_FUNC</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-filter.md">D3D10_DDI_FILTER</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-texture-address-mode.md">D3D10_DDI_TEXTURE_ADDRESS_MODE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_SAMPLER_DESC structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
