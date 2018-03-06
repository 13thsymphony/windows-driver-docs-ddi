---
UID: NE:d3d10umddi.D3D11_DDI_SHADER_MIN_PRECISION
title: D3D11_DDI_SHADER_MIN_PRECISION
author: windows-driver-content
description: Specifies minimum precision levels that the user-mode driver supports in shaders.
old-location: display\d3d11_ddi_shader_min_precision.htm
old-project: display
ms.assetid: cf77d6c7-8f42-470a-9e3a-85d95398470b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_DDI_SHADER_MIN_PRECISION, D3D11_DDI_SHADER_MIN_PRECISION enumeration [Display Devices], D3D11_DDI_SHADER_MIN_PRECISION_10_BIT, D3D11_DDI_SHADER_MIN_PRECISION_16_BIT, d3d10umddi/D3D11_DDI_SHADER_MIN_PRECISION, d3d10umddi/D3D11_DDI_SHADER_MIN_PRECISION_10_BIT, d3d10umddi/D3D11_DDI_SHADER_MIN_PRECISION_16_BIT, display.d3d11_ddi_shader_min_precision
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_DDI_SHADER_MIN_PRECISION
product: Windows
targetos: Windows
req.typenames: D3D11_DDI_SHADER_MIN_PRECISION
---

# D3D11_DDI_SHADER_MIN_PRECISION Enumeration
Specifies minimum precision levels that the user-mode driver supports in shaders.

## Syntax
````
typedef enum D3D11_DDI_SHADER_MIN_PRECISION { 
  D3D11_DDI_SHADER_MIN_PRECISION_10_BIT  = 0x1,
  D3D11_DDI_SHADER_MIN_PRECISION_16_BIT  = 0x2
} D3D11_DDI_SHADER_MIN_PRECISION;
````

## Constants

<table>
            
                <tr>
                    <td>D3D11_DDI_SHADER_MIN_PRECISION_10_BIT</td>
                    <td>The minimum precision level is 10-bit.</td>
                </tr>
            
                <tr>
                    <td>D3D11_DDI_SHADER_MIN_PRECISION_16_BIT</td>
                    <td>The minimum precision level is 16-bit.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |