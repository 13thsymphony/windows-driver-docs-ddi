---
UID: NE:d3d12umddi.D3D12DDI_TEXTURE_LAYOUT
title: D3D12DDI_TEXTURE_LAYOUT
author: windows-driver-content
description: Specifies a texture layout.
old-location: display\d3d12ddi_texture_layout.htm
old-project: display
ms.assetid: F039A0D9-D1AE-4940-B67D-30CC6344EC7D
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_TL_64KB_TILE_UNDEFINED_SWIZZLE, display.d3d12ddi_texture_layout, d3d12umddi/D3D12DDI_TL_UNDEFINED, D3D12DDI_TEXTURE_LAYOUT, D3D12DDI_TL_ROW_MAJOR, D3D12DDI_TL_DEVICE_DEPENDENT_SWIZZLE_0, d3d12umddi/D3D12DDI_TL_64KB_TILE_STANDARD_SWIZZLE, d3d12umddi/D3D12DDI_TL_64KB_TILE_UNDEFINED_SWIZZLE, D3D12DDI_TEXTURE_LAYOUT enumeration [Display Devices], d3d12umddi/D3D12DDI_TL_DEVICE_DEPENDENT_SWIZZLE_0, D3D12DDI_TL_64KB_TILE_STANDARD_SWIZZLE, D3D12DDI_TL_UNDEFINED, d3d12umddi/D3D12DDI_TEXTURE_LAYOUT, d3d12umddi/D3D12DDI_TL_ROW_MAJOR
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_TEXTURE_LAYOUT
product: Windows
targetos: Windows
req.typenames: D3D12DDI_TEXTURE_LAYOUT
---

# D3D12DDI_TEXTURE_LAYOUT Enumeration
Specifies a texture layout.

## Syntax
````
typedef enum D3D12DDI_TEXTURE_LAYOUT { 
  D3D12DDI_TL_UNDEFINED                    = 0,
  D3D12DDI_TL_ROW_MAJOR                    = 1,
  D3D12DDI_TL_64KB_TILE_UNDEFINED_SWIZZLE  = 2,
  D3D12DDI_TL_64KB_TILE_STANDARD_SWIZZLE   = 3,
  D3D12DDI_TL_DEVICE_DEPENDENT_SWIZZLE_0   = 0x100
} D3D12DDI_TEXTURE_LAYOUT;
````

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_TL_64KB_TILE_STANDARD_SWIZZLE</td>
                    <td>A 64 KB tile with standard swizzle.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_TL_64KB_TILE_UNDEFINED_SWIZZLE</td>
                    <td>A 64 KB tile with undefined swizzle.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_TL_DEVICE_DEPENDENT_SWIZZLE_0</td>
                    <td>A device dependant swizzle.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_TL_ROW_MAJOR</td>
                    <td>Texture layout row major.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_TL_UNDEFINED</td>
                    <td>Texture layout undefined.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |