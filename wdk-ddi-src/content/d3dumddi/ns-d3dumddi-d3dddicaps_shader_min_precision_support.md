---
UID: NS:d3dumddi.D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT
title: D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT
author: windows-driver-content
description: Describes precision support options for shaders in the user-mode display driver.
old-location: display\d3dddicaps_shader_min_precision_support.htm
old-project: display
ms.assetid: c3ad65e7-8a91-464b-9a7f-e5c47ee54048
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT, D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT structure [Display Devices], d3dumddi/D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT, display.d3dddicaps_shader_min_precision_support
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dumddi.h
api_name:
-	D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT
product: Windows
targetos: Windows
req.typenames: D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT
---

# D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT structure
Describes precision support options for shaders in the user-mode display driver.

## Syntax
````
typedef struct D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT {
  UINT VertexShaderMinPrecision;
  UINT PixelShaderMinPrecision;
} D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT;
````

## Members


`VertexShaderMinPrecision`

A combination of values of type <a href="..\d3dumddi\ne-d3dumddi-d3dddicaps_shader_min_precision.md">D3DDDICAPS_SHADER_MIN_PRECISION</a> that are combined by using a bitwise OR operation. The resulting value specifies minimum precision levels that the driver supports for the vertex shader. A value of zero indicates that the driver supports only the default precision for the shader model, and not a lower precision.

`PixelShaderMinPrecision`

A combination of values of type <a href="..\d3dumddi\ne-d3dumddi-d3dddicaps_shader_min_precision.md">D3DDDICAPS_SHADER_MIN_PRECISION</a> that are combined by using a bitwise OR operation. The resulting value specifies minimum precision levels that the driver supports for the pixel shader. A value of zero indicates that the driver supports only the default precision for the shader model, and not a lower precision.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ne-d3dumddi-d3dddicaps_shader_min_precision.md">D3DDDICAPS_SHADER_MIN_PRECISION</a>