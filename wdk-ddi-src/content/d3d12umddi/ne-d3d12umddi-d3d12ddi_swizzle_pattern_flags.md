---
UID: NE:d3d12umddi.D3D12DDI_SWIZZLE_PATTERN_FLAGS
title: D3D12DDI_SWIZZLE_PATTERN_FLAGS
author: windows-driver-content
description: Specifies swizzle pattern flags.
old-location: display\d3d12ddi_swizzle_pattern_flags.htm
old-project: display
ms.assetid: 613FE631-8381-4EDD-85C9-7B91F9F8B92F
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d12umddi/D3D12DDI_SWIZZLE_PATTERN_FLAGS_NONE, D3D12DDI_SWIZZLE_PATTERN_FLAGS, display.d3d12ddi_swizzle_pattern_flags, D3D12DDI_SWIZZLE_PATTERN_FLAGS enumeration [Display Devices], d3d12umddi/D3D12DDI_SWIZZLE_PATTERN_FLAGS_STACK_DEPTH_SLICES, D3D12DDI_SWIZZLE_PATTERN_FLAGS_NONE, d3d12umddi/D3D12DDI_SWIZZLE_PATTERN_FLAGS, D3D12DDI_SWIZZLE_PATTERN_FLAGS_STACK_DEPTH_SLICES
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
-	D3D12DDI_SWIZZLE_PATTERN_FLAGS
product: Windows
targetos: Windows
req.typenames: D3D12DDI_SWIZZLE_PATTERN_FLAGS
---

# D3D12DDI_SWIZZLE_PATTERN_FLAGS Enumeration
Specifies swizzle pattern flags.

## Syntax
````
typedef enum D3D12DDI_SWIZZLE_PATTERN_FLAGS { 
  D3D12DDI_SWIZZLE_PATTERN_FLAGS_NONE                = 0,
  D3D12DDI_SWIZZLE_PATTERN_FLAGS_STACK_DEPTH_SLICES  = 0x1
} D3D12DDI_SWIZZLE_PATTERN_FLAGS;
````

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_SWIZZLE_PATTERN_FLAGS_0022_CONDITIONAL_POSTAMBLE_XORS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_SWIZZLE_PATTERN_FLAGS_NONE</td>
                    <td>No flag value.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_SWIZZLE_PATTERN_FLAGS_STACK_DEPTH_SLICES</td>
                    <td>Depth slices are treated as being stacked vertically prior to swizzling.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |