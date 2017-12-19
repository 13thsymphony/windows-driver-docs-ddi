---
UID: NE.d3d12umddi.D3D12DDI_RESOURCE_FLAGS_0003
title: D3D12DDI_RESOURCE_FLAGS_0003
author: windows-driver-content
description: Specifies resource flag values.
old-location: display\d3d12ddi_resource_flags_0003.htm
old-project: display
ms.assetid: 595A4177-4A18-48D6-8B5C-D7D2FBD9FE9B
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D12DDI_RESOURCE_FLAGS_0003, D3D12DDI_RESOURCE_FLAGS_0003
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
req.alt-api: D3D12DDI_RESOURCE_FLAGS_0003
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
---

# D3D12DDI_RESOURCE_FLAGS_0003 enumeration



## -description
Specifies resource flag values.



## -syntax

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


## -enum-fields

### -field D3D12DDI_RESOURCE_FLAG_0003_NONE

Constant for no flags.


### -field D3D12DDI_RESOURCE_FLAG_0003_RENDER_TARGET

Render target.


### -field D3D12DDI_RESOURCE_FLAG_0003_DEPTH_STENCIL

Depth stencil.


### -field D3D12DDI_RESOURCE_FLAG_0003_CROSS_ADAPTER

Cross adapter.


### -field D3D12DDI_RESOURCE_FLAG_0003_SIMULTANEOUS_ACCESS

Simultaneous access.


### -field D3D12DDI_RESOURCE_FLAG_0003_SHADER_RESOURCE

Shader resource.


### -field D3D12DDI_RESOURCE_FLAG_0020_VIDEO_DECODE_REFERENCE_ONLY

Video decode reference only.


### -field D3D12DDI_RESOURCE_FLAG_0020_CONTENT_PROTECTION 

Content protection.


### -field D3D12DDI_RESOURCE_FLAG_0022_UNORDERED_ACCESS

Unordered access. This value is available as a resource flag for the fallback plans.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>