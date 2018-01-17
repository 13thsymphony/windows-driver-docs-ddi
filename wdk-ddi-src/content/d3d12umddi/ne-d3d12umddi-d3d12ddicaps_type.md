---
UID: NE:d3d12umddi.D3D12DDICAPS_TYPE
title: D3D12DDICAPS_TYPE
author: windows-driver-content
description: Specifies a capability type.
old-location: display\d3d12ddicaps_type.htm
old-project: display
ms.assetid: C74697BF-A191-4371-9F23-7F655EBC53B3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDICAPS_TYPE, D3D12DDICAPS_TYPE
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
req.alt-api: D3D12DDICAPS_TYPE
req.alt-loc: D3d12umddi.h
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
req.typenames: D3D12DDICAPS_TYPE
---

# D3D12DDICAPS_TYPE enumeration



## -description
Specifies a capability type. 



## -syntax

````
typedef enum D3D12DDICAPS_TYPE { 
  D3D12DDICAPS_TYPE_TEXTURE_LAYOUT                         = 1000,
  D3D12DDICAPS_TYPE_SWIZZLE_PATTERN                        = 1001,
  D3D12DDICAPS_TYPE_MEMORY_ARCHITECTURE                    = 1002,
  D3D12DDICAPS_TYPE_TEXTURE_LAYOUT_SETS                    = 1003,
  D3D12DDICAPS_TYPE_SHADER                                 = 1004,
  D3D12DDICAPS_TYPE_ARCHITECTURE_INFO                      = 1005,
  D3D12DDICAPS_TYPE_D3D12_OPTIONS                          = 1006,
  D3D12DDICAPS_TYPE_3DPIPELINESUPPORT                      = 1007,
  D3D12DDICAPS_TYPE_JPEG_OPTIONS                           = 1008,
  D3D12DDICAPS_TYPE_GPUVA_CAPS                             = 1009,
  D3D12DDICAPS_TYPE_TEXTURE_LAYOUT1                        = 1010,
  D3D12DDICAPS_TYPE_0011_SHADER_MODELS                     = 1012,
  D3D12DDICAPS_TYPE_0020_CONTENT_PROTECTION_SUPPORT        = 1057,
  D3D12DDICAPS_TYPE_0020_CONTENT_PROTECTION_DRM_SUPPORT    = 1058,
  D3D12DDICAPS_TYPE_0022_CPU_PAGE_TABLE_FALSE_POSITIVES    = 1059,
  D3D12DDICAPS_TYPE_0022_TEXTURE_LAYOUT                    = 1060,
  D3D12DDICAPS_TYPE_0022_SWIZZLE_PATTERN                   = 1061,
  D3D12DDICAPS_TYPE_0023_UMD_BASED_COMMAND_QUEUE_PRIORITY  = 1062
} D3D12DDICAPS_TYPE;
````


## -enum-fields

### -field D3D12DDICAPS_TYPE_TEXTURE_LAYOUT

Texture layout.


### -field D3D12DDICAPS_TYPE_SWIZZLE_PATTERN

Swizzle pattern.


### -field D3D12DDICAPS_TYPE_MEMORY_ARCHITECTURE

Memory architecture.


### -field D3D12DDICAPS_TYPE_TEXTURE_LAYOUT_SETS

Texture layout sets.


### -field D3D12DDICAPS_TYPE_SHADER

Shader.


### -field D3D12DDICAPS_TYPE_ARCHITECTURE_INFO

Architecture information.


### -field D3D12DDICAPS_TYPE_D3D12_OPTIONS

Options for D3D12.


### -field D3D12DDICAPS_TYPE_3DPIPELINESUPPORT

Support for 3D pipeline.


### -field D3D12DDICAPS_TYPE_JPEG_OPTIONS

JPEG options.


### -field D3D12DDICAPS_TYPE_GPUVA_CAPS

GPU video acceleration capabilities.


### -field D3D12DDICAPS_TYPE_TEXTURE_LAYOUT1

Texture layout.


### -field D3D12DDICAPS_TYPE_0011_SHADER_MODELS

Shader models.


### -field D3D12DDICAPS_TYPE_0020_CONTENT_PROTECTION_SUPPORT

Content protection support.


### -field D3D12DDICAPS_TYPE_0020_CONTENT_PROTECTION_DRM_SUPPORT

Content protection digital rights management (DRM) support.


### -field D3D12DDICAPS_TYPE_0022_CPU_PAGE_TABLE_FALSE_POSITIVES

CPU page table false positives.


### -field D3D12DDICAPS_TYPE_0022_TEXTURE_LAYOUT

Texture layout.


### -field D3D12DDICAPS_TYPE_0022_SWIZZLE_PATTERN

Swizzle pattern.


### -field D3D12DDICAPS_TYPE_0023_UMD_BASED_COMMAND_QUEUE_PRIORITY

UMD-based command queue priority. 


## -remarks
