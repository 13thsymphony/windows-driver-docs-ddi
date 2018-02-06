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
ms.keywords: d3d10umddi/D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA, display.d3d11_ddi_shader_min_precision_support_data, D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA, D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA structure [Display Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA
product: Windows
targetos: Windows
req.typenames: D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA
---

# D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA structure
Describes precision support options for shaders in the user-mode display driver.

## Syntax
````
typedef struct D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA {
  UINT PixelShaderMinPrecision;
  UINT AllOtherStagesMinPrecision;
} D3D11_DDI_SHADER_MIN_PRECISION_SUPPORT_DATA;
````

## Members


`AllOtherStagesMinPrecision`

A combination of values of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_ddi_shader_min_precision.md">D3D11_DDI_SHADER_MIN_PRECISION</a> that are combined by using a bitwise <b>OR</b> operation. The resulting value specifies minimum precision levels that the driver supports for all other stages in the video processing pipeline that are not pixel shaders. A value of zero indicates that the driver supports only the default precision for the shader model, and not a lower precision.

`PixelShaderMinPrecision`

A combination of values of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_ddi_shader_min_precision.md">D3D11_DDI_SHADER_MIN_PRECISION</a> that are combined by using a bitwise <b>OR</b> operation. The resulting value specifies minimum precision levels that the driver supports for the pixel shader. A value of zero indicates that the driver supports only the default precision for the shader model, and not a lower precision.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |