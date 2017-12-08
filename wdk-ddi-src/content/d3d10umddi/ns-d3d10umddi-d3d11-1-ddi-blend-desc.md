---
UID: NS.d3d10umddi.D3D11_1_DDI_BLEND_DESC
title: D3D11_1_DDI_BLEND_DESC
author: windows-driver-content
description: Describes a blend state. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\d3d11_1_ddi_blend_desc.htm
old-project: display
ms.assetid: 1f633261-82b2-4346-b1c2-cd36228af5f4
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D11_1_DDI_BLEND_DESC, D3D11_1_DDI_BLEND_DESC
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
req.alt-api: D3D11_1_DDI_BLEND_DESC
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

# D3D11_1_DDI_BLEND_DESC structure



## -description
<p> Describes a blend state. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.</p>


## -syntax

````
typedef struct D3D11_1_DDI_BLEND_DESC {
  BOOL                                 AlphaToCoverageEnable;
  BOOL                                 IndependentBlendEnable;
  D3D11_1_DDI_RENDER_TARGET_BLEND_DESC RenderTarget[D3D10_DDI_SIMULTANEOUS_RENDER_TARGET_COUNT];
} D3D11_1_DDI_BLEND_DESC;
````


## -struct-fields
<dl>

### -field AlphaToCoverageEnable

<dd>
<p>[in] A Boolean value that specifies whether transparency coverage is enabled. <b>TRUE</b> indicates transparency coverage is enabled; <b>FALSE</b> indicates transparency coverage is disabled. This member is relevant for multiple-sample antialiasing only.</p>
</dd>

### -field IndependentBlendEnable

<dd>
<p>[in] A Boolean value that specifies only whether the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11-1ddi-calcprivateblendstatesize.md">CalcPrivateBlendStateSize(D3D11_1)</a> function replicated the first entry in the array that the <b>RenderTarget</b> member specifies to the other entries of that array. <b>TRUE</b> indicates the first entry was not replicated; <b>FALSE</b> indicates that the first entry in the array in the <b>RenderTarget</b> member is replicated to the other entries of the array.</p>
</dd>

### -field RenderTarget

<dd>
<p>[in] An array of <a href="..\d3d10umddi\ns-d3d10umddi-d3d11-1-ddi-render-target-blend-desc.md">D3D11_1_DDI_RENDER_TARGET_BLEND_DESC</a> structures that indicate the blend state for each associated render target.</p>
</dd>
</dl>

## -remarks


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

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11-1ddi-calcprivateblendstatesize.md">CalcPrivateBlendStateSize(D3D11_1)</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11-1ddi-createblendstate.md">CreateBlendState(D3D11_1)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11-1-ddi-render-target-blend-desc.md">D3D11_1_DDI_RENDER_TARGET_BLEND_DESC</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1_DDI_BLEND_DESC structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
