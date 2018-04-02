---
UID: NE:d3d12umddi.D3D12DDI_CREATE_SHADER_FLAGS
title: D3D12DDI_CREATE_SHADER_FLAGS
author: windows-driver-content
description: Defines flags for shader creation.
old-location: display\d3d12ddi_create_shader_flags.htm
old-project: display
ms.assetid: 93F27775-3E74-4310-8E09-DCB079436706
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_CREATE_SHADER_FLAGS, D3D12DDI_CREATE_SHADER_FLAGS enumeration [Display Devices], D3D12DDI_CREATE_SHADER_FLAG_DISABLE_OPTIMIZATION, D3D12DDI_CREATE_SHADER_FLAG_ENABLE_SHADER_TRACING, D3D12DDI_CREATE_SHADER_FLAG_NONE, d3d12umddi/D3D12DDI_CREATE_SHADER_FLAGS, d3d12umddi/D3D12DDI_CREATE_SHADER_FLAG_DISABLE_OPTIMIZATION, d3d12umddi/D3D12DDI_CREATE_SHADER_FLAG_ENABLE_SHADER_TRACING, d3d12umddi/D3D12DDI_CREATE_SHADER_FLAG_NONE, display.d3d12ddi_create_shader_flags
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
-	D3D12DDI_CREATE_SHADER_FLAGS
product: Windows
targetos: Windows
req.typenames: D3D12DDI_CREATE_SHADER_FLAGS
---

# D3D12DDI_CREATE_SHADER_FLAGS Enumeration
Defines flags for shader creation.

## Syntax
```
typedef enum D3D12DDI_CREATE_SHADER_FLAGS {
  D3D12DDI_CREATE_SHADER_FLAG_NONE                       ,
  D3D12DDI_CREATE_SHADER_FLAG_ENABLE_SHADER_TRACING      ,
  D3D12DDI_CREATE_SHADER_FLAG_DISABLE_OPTIMIZATION_0024
} ;
```

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_CREATE_SHADER_FLAG_NONE</td>
                    <td>No flag value for shader creation.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_CREATE_SHADER_FLAG_ENABLE_SHADER_TRACING</td>
                    <td>The shader is tracing.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_CREATE_SHADER_FLAG_DISABLE_OPTIMIZATION_0024</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |