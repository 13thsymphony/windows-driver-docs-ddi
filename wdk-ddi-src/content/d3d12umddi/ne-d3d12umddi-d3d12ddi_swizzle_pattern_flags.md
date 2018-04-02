---
UID: NE:d3d12umddi.D3D12DDI_SWIZZLE_PATTERN_FLAGS
title: D3D12DDI_SWIZZLE_PATTERN_FLAGS
author: windows-driver-content
description: Specifies swizzle pattern flags.
old-location: display\d3d12ddi_swizzle_pattern_flags.htm
old-project: display
ms.assetid: 613FE631-8381-4EDD-85C9-7B91F9F8B92F
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_SWIZZLE_PATTERN_FLAGS, D3D12DDI_SWIZZLE_PATTERN_FLAGS enumeration [Display Devices], D3D12DDI_SWIZZLE_PATTERN_FLAGS_NONE, D3D12DDI_SWIZZLE_PATTERN_FLAGS_STACK_DEPTH_SLICES, d3d12umddi/D3D12DDI_SWIZZLE_PATTERN_FLAGS, d3d12umddi/D3D12DDI_SWIZZLE_PATTERN_FLAGS_NONE, d3d12umddi/D3D12DDI_SWIZZLE_PATTERN_FLAGS_STACK_DEPTH_SLICES, display.d3d12ddi_swizzle_pattern_flags
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
-	D3D12DDI_SWIZZLE_PATTERN_FLAGS
product: Windows
targetos: Windows
req.typenames: D3D12DDI_SWIZZLE_PATTERN_FLAGS
---

# D3D12DDI_SWIZZLE_PATTERN_FLAGS Enumeration
Specifies swizzle pattern flags.

## Syntax
```
typedef enum D3D12DDI_SWIZZLE_PATTERN_FLAGS {
  D3D12DDI_SWIZZLE_PATTERN_FLAGS_NONE                             ,
  D3D12DDI_SWIZZLE_PATTERN_FLAGS_STACK_DEPTH_SLICES               ,
  D3D12DDI_SWIZZLE_PATTERN_FLAGS_0022_CONDITIONAL_POSTAMBLE_XORS
} ;
```

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_SWIZZLE_PATTERN_FLAGS_NONE</td>
                    <td>No flag value.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_SWIZZLE_PATTERN_FLAGS_STACK_DEPTH_SLICES</td>
                    <td>Depth slices are treated as being stacked vertically prior to swizzling.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_SWIZZLE_PATTERN_FLAGS_0022_CONDITIONAL_POSTAMBLE_XORS</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |