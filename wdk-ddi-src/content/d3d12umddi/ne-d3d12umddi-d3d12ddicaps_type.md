---
UID: NE:d3d12umddi.D3D12DDICAPS_TYPE
title: D3D12DDICAPS_TYPE
author: windows-driver-content
description: Specifies a capability type.
old-location: display\d3d12ddicaps_type.htm
old-project: display
ms.assetid: C74697BF-A191-4371-9F23-7F655EBC53B3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDICAPS_TYPE, D3D12DDICAPS_TYPE enumeration [Display Devices], D3D12DDICAPS_TYPE_0011_SHADER_MODELS, D3D12DDICAPS_TYPE_0020_CONTENT_PROTECTION_DRM_SUPPORT, D3D12DDICAPS_TYPE_0020_CONTENT_PROTECTION_SUPPORT, D3D12DDICAPS_TYPE_0022_CPU_PAGE_TABLE_FALSE_POSITIVES, D3D12DDICAPS_TYPE_0022_SWIZZLE_PATTERN, D3D12DDICAPS_TYPE_0022_TEXTURE_LAYOUT, D3D12DDICAPS_TYPE_0023_UMD_BASED_COMMAND_QUEUE_PRIORITY, D3D12DDICAPS_TYPE_3DPIPELINESUPPORT, D3D12DDICAPS_TYPE_ARCHITECTURE_INFO, D3D12DDICAPS_TYPE_D3D12_OPTIONS, D3D12DDICAPS_TYPE_GPUVA_CAPS, D3D12DDICAPS_TYPE_JPEG_OPTIONS, D3D12DDICAPS_TYPE_MEMORY_ARCHITECTURE, D3D12DDICAPS_TYPE_SHADER, D3D12DDICAPS_TYPE_SWIZZLE_PATTERN, D3D12DDICAPS_TYPE_TEXTURE_LAYOUT, D3D12DDICAPS_TYPE_TEXTURE_LAYOUT1, D3D12DDICAPS_TYPE_TEXTURE_LAYOUT_SETS, d3d12umddi/D3D12DDICAPS_TYPE, d3d12umddi/D3D12DDICAPS_TYPE_0011_SHADER_MODELS, d3d12umddi/D3D12DDICAPS_TYPE_0020_CONTENT_PROTECTION_DRM_SUPPORT, d3d12umddi/D3D12DDICAPS_TYPE_0020_CONTENT_PROTECTION_SUPPORT, d3d12umddi/D3D12DDICAPS_TYPE_0022_CPU_PAGE_TABLE_FALSE_POSITIVES, d3d12umddi/D3D12DDICAPS_TYPE_0022_SWIZZLE_PATTERN, d3d12umddi/D3D12DDICAPS_TYPE_0022_TEXTURE_LAYOUT, d3d12umddi/D3D12DDICAPS_TYPE_0023_UMD_BASED_COMMAND_QUEUE_PRIORITY, d3d12umddi/D3D12DDICAPS_TYPE_3DPIPELINESUPPORT, d3d12umddi/D3D12DDICAPS_TYPE_ARCHITECTURE_INFO, d3d12umddi/D3D12DDICAPS_TYPE_D3D12_OPTIONS, d3d12umddi/D3D12DDICAPS_TYPE_GPUVA_CAPS, d3d12umddi/D3D12DDICAPS_TYPE_JPEG_OPTIONS, d3d12umddi/D3D12DDICAPS_TYPE_MEMORY_ARCHITECTURE, d3d12umddi/D3D12DDICAPS_TYPE_SHADER, d3d12umddi/D3D12DDICAPS_TYPE_SWIZZLE_PATTERN, d3d12umddi/D3D12DDICAPS_TYPE_TEXTURE_LAYOUT, d3d12umddi/D3D12DDICAPS_TYPE_TEXTURE_LAYOUT1, d3d12umddi/D3D12DDICAPS_TYPE_TEXTURE_LAYOUT_SETS, display.d3d12ddicaps_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
-	D3d12umddi.h
api_name:
-	D3D12DDICAPS_TYPE
product: Windows
targetos: Windows
req.typenames: D3D12DDICAPS_TYPE
---

# D3D12DDICAPS_TYPE Enumeration
Specifies a capability type.

## Syntax
```
typedef enum D3D12DDICAPS_TYPE {
  D3D12DDICAPS_TYPE_TEXTURE_LAYOUT                           ,
  D3D12DDICAPS_TYPE_SWIZZLE_PATTERN                          ,
  D3D12DDICAPS_TYPE_MEMORY_ARCHITECTURE                      ,
  D3D12DDICAPS_TYPE_TEXTURE_LAYOUT_SETS                      ,
  D3D12DDICAPS_TYPE_SHADER                                   ,
  D3D12DDICAPS_TYPE_ARCHITECTURE_INFO                        ,
  D3D12DDICAPS_TYPE_D3D12_OPTIONS                            ,
  D3D12DDICAPS_TYPE_3DPIPELINESUPPORT                        ,
  D3D12DDICAPS_TYPE_GPUVA_CAPS                               ,
  D3D12DDICAPS_TYPE_TEXTURE_LAYOUT1                          ,
  D3D12DDICAPS_TYPE_0011_SHADER_MODELS                       ,
  D3D12DDICAPS_TYPE_0030_PROTECTED_RESOURCE_SESSION_SUPPORT  ,
  D3D12DDICAPS_TYPE_0030_CRYPTO_SESSION_SUPPORT              ,
  D3D12DDICAPS_TYPE_0022_CPU_PAGE_TABLE_FALSE_POSITIVES      ,
  D3D12DDICAPS_TYPE_0022_TEXTURE_LAYOUT                      ,
  D3D12DDICAPS_TYPE_0022_SWIZZLE_PATTERN                     ,
  D3D12DDICAPS_TYPE_0023_UMD_BASED_COMMAND_QUEUE_PRIORITY    ,
  D3D12DDICAPS_TYPE_0030_CONTENT_PROTECTION_SYSTEM_COUNT     ,
  D3D12DDICAPS_TYPE_0030_CONTENT_PROTECTION_SYSTEM_SUPPORT   ,
  D3D12DDICAPS_TYPE_0030_CRYPTO_SESSION_TRANSFORM_SUPPORT
} ;
```

## Constants

<table>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_TEXTURE_LAYOUT</td>
                    <td>Texture layout.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_SWIZZLE_PATTERN</td>
                    <td>Swizzle pattern.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_MEMORY_ARCHITECTURE</td>
                    <td>Memory architecture.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_TEXTURE_LAYOUT_SETS</td>
                    <td>Texture layout sets.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_SHADER</td>
                    <td>Shader.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_ARCHITECTURE_INFO</td>
                    <td>Architecture information.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_D3D12_OPTIONS</td>
                    <td>Options for D3D12.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_3DPIPELINESUPPORT</td>
                    <td>Support for 3D pipeline.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_GPUVA_CAPS</td>
                    <td>GPU video acceleration capabilities.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_TEXTURE_LAYOUT1</td>
                    <td>Texture layout.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_0011_SHADER_MODELS</td>
                    <td>Shader models.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_0030_PROTECTED_RESOURCE_SESSION_SUPPORT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_0030_CRYPTO_SESSION_SUPPORT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_0022_CPU_PAGE_TABLE_FALSE_POSITIVES</td>
                    <td>CPU page table false positives.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_0022_TEXTURE_LAYOUT</td>
                    <td>Texture layout.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_0022_SWIZZLE_PATTERN</td>
                    <td>Swizzle pattern.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_0023_UMD_BASED_COMMAND_QUEUE_PRIORITY</td>
                    <td>UMD-based command queue priority.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_0030_CONTENT_PROTECTION_SYSTEM_COUNT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_0030_CONTENT_PROTECTION_SYSTEM_SUPPORT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3D12DDICAPS_TYPE_0030_CRYPTO_SESSION_TRANSFORM_SUPPORT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |