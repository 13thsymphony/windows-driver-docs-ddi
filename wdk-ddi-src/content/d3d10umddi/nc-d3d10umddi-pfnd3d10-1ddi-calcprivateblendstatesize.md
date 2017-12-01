---
UID: NC.d3d10umddi.PFND3D10_1DDI_CALCPRIVATEBLENDSTATESIZE
title: PFND3D10_1DDI_CALCPRIVATEBLENDSTATESIZE
author: windows-driver-content
description: The CalcPrivateBlendStateSize(D3D10_1) function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.
old-location: display\calcprivateblendstatesize_d3d10_1_.htm
old-project: display
ms.assetid: 6f48290e-d571-4e59-9f33-58398db5b6fb
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateBlendStateSize(D3D10_1) is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CalcPrivateBlendStateSize_d3d10_1_
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

# PFND3D10_1DDI_CALCPRIVATEBLENDSTATESIZE callback



## -description
<p>The <b>CalcPrivateBlendStateSize(D3D10_1)</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.</p>


## -prototype

````
PFND3D10_1DDI_CALCPRIVATEBLENDSTATESIZE CalcPrivateBlendStateSize_d3d10_1_;

SIZE_T APIENTRY CalcPrivateBlendStateSize_d3d10_1_(
  _In_       D3D10DDI_HDEVICE       hDevice,
  _In_ const D3D10_1_DDI_BLEND_DESC *pBlendDesc
)
{ ... }
````


## -parameters
<dl>

### -param <i>hDevice</i> [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param <i>pBlendDesc</i> [in]

<dd>
<p> A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10-1-ddi-blend-desc.md">D3D10_1_DDI_BLEND_DESC</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. </p>
</dd>
</dl>

## -returns
<p><b>CalcPrivateBlendStateSize(D3D10_1)</b> returns the size of the memory region that the driver requires for creating a blend state.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p><i>CalcPrivateBlendStateSize(D3D10_1)</i> is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions. </p>
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
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10-1-ddi-blend-desc.md">D3D10_1_DDI_BLEND_DESC</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10-1ddi-devicefuncs.md">D3D10_1DDI_DEVICEFUNCS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10_1DDI_CALCPRIVATEBLENDSTATESIZE callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
