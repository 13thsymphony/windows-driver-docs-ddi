---
UID: NE:d3d12umddi.D3D12DDI_RESOURCE_FLAGS_0003
title: D3D12DDI_RESOURCE_FLAGS_0003
author: windows-driver-content
description: Specifies resource flag values.
old-location: display\d3d12ddi_resource_flags_0003.htm
old-project: display
ms.assetid: 595A4177-4A18-48D6-8B5C-D7D2FBD9FE9B
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_RESOURCE_FLAG_0020_CONTENT_PROTECTION, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_NONE, D3D12DDI_RESOURCE_FLAG_0003_RENDER_TARGET, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_SIMULTANEOUS_ACCESS, D3D12DDI_RESOURCE_FLAGS_0003, d3d12umddi/D3D12DDI_RESOURCE_FLAGS_0003, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0020_CONTENT_PROTECTION, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0022_UNORDERED_ACCESS, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_CROSS_ADAPTER, D3D12DDI_RESOURCE_FLAG_0003_SHADER_RESOURCE, D3D12DDI_RESOURCE_FLAG_0022_UNORDERED_ACCESS, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_DEPTH_STENCIL, D3D12DDI_RESOURCE_FLAGS_0003 enumeration [Display Devices], D3D12DDI_RESOURCE_FLAG_0020_VIDEO_DECODE_REFERENCE_ONLY, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0020_VIDEO_DECODE_REFERENCE_ONLY, D3D12DDI_RESOURCE_FLAG_0003_NONE, D3D12DDI_RESOURCE_FLAG_0003_SIMULTANEOUS_ACCESS, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_SHADER_RESOURCE, display.d3d12ddi_resource_flags_0003, D3D12DDI_RESOURCE_FLAG_0003_DEPTH_STENCIL, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_RENDER_TARGET, D3D12DDI_RESOURCE_FLAG_0003_CROSS_ADAPTER
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
-	D3D12DDI_RESOURCE_FLAGS_0003
product: Windows
targetos: Windows
req.typenames: D3D12DDI_RESOURCE_FLAGS_0003
---

# D3D12DDI_RESOURCE_FLAGS_0003 Enumeration
Specifies resource flag values.

## Syntax
````
typedef enum D3D12DDI_RESOURCE_FLAGS_0003 { 
  D3D12DDI_RESOURCE_FLAG_0003_NONE                         = 0x0,
  D3D12DDI_RESOURCE_FLAG_0003_RENDER_TARGET                = 0x1,
  D3D12DDI_RESOURCE_FLAG_0003_DEPTH_STENCIL                = 0x2,
  D3D12DDI_RESOURCE_FLAG_0003_CROSS_ADAPTER                = 0x4,
  D3D12DDI_RESOURCE_FLAG_0003_SIMULTANEOUS_ACCESS          = 0x8,
  D3D12DDI_RESOURCE_FLAG_0003_SHADER_RESOURCE              = 0x10,
  D3D12DDI_RESOURCE_FLAG_0020_VIDEO_DECODE_REFERENCE_ONLY  = 0x20,
  D3D12DDI_RESOURCE_FLAG_0020_CONTENT_PROTECTION           = 0x40,
  D3D12DDI_RESOURCE_FLAG_0022_UNORDERED_ACCESS             = 0x80
} D3D12DDI_RESOURCE_FLAGS_0003;
````

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_FLAG_0003_CROSS_ADAPTER</td>
                    <td>Cross adapter.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_FLAG_0003_DEPTH_STENCIL</td>
                    <td>Depth stencil.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_FLAG_0003_NONE</td>
                    <td>Constant for no flags.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_FLAG_0003_RENDER_TARGET</td>
                    <td>Render target.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_FLAG_0003_SHADER_RESOURCE</td>
                    <td>Shader resource.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_FLAG_0003_SIMULTANEOUS_ACCESS</td>
                    <td>Simultaneous access.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_FLAG_0020_CONTENT_PROTECTION</td>
                    <td>Content protection.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_FLAG_0020_VIDEO_DECODE_REFERENCE_ONLY</td>
                    <td>Video decode reference only.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_FLAG_0022_UNORDERED_ACCESS</td>
                    <td>Unordered access. This value is available as a resource flag for the fallback plans.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |