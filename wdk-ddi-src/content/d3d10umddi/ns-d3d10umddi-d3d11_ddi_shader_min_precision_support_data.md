---
UID: NS:d3d10umddi.D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA
title: D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA
author: windows-driver-content
description: Describes precision support options for shaders in the user-mode display driver.
old-location: display\d3d11_ddi_shader_min_precision_support_data.htm
old-project: display
ms.assetid: e93649d1-4ad0-4873-99c7-b2f3ed48aac6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA, D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA
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
req.alt-api: D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA
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
req.typenames: D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA
---

# D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA structure



## -description
Describes precision support options for shaders in the user-mode display driver.



## -syntax

````
typedef struct D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA {
  UINT PixelShaderMinPrecision;
  UINT AllOtherStagesMinPrecision;
} D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA;
````


## -struct-fields

### -field PixelShaderMinPrecision

A combination of values of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_ddi_shader_min_precision.md">D3D11_DDI_SHADER_MIN_PRECISION</a> that are combined by using a bitwise <b>OR</b> operation. The resulting value specifies minimum precision levels that the driver supports for the pixel shader. A value of zero indicates that the driver supports only the default precision for the shader model, and not a lower precision.


### -field AllOtherStagesMinPrecision

A combination of values of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_ddi_shader_min_precision.md">D3D11_DDI_SHADER_MIN_PRECISION</a> that are combined by using a bitwise <b>OR</b> operation. The resulting value specifies minimum precision levels that the driver supports for all other stages in the video processing pipeline that are not pixel shaders. A value of zero indicates that the driver supports only the default precision for the shader model, and not a lower precision.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>