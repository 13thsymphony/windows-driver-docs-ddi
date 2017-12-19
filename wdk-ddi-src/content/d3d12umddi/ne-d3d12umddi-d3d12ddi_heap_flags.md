---
UID: NE.d3d12umddi.D3D12DDI_HEAP_FLAGS
title: D3D12DDI_HEAP_FLAGS
author: windows-driver-content
description: Contains Direct3D 12 heap flags.
old-location: display\d3d12ddi_heap_flags.htm
old-project: display
ms.assetid: 8224E497-7F52-469B-98C9-ECC5F1970894
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D12DDI_HEAP_FLAGS, D3D12DDI_HEAP_FLAGS
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
req.alt-api: D3D12DDI_HEAP_FLAGS
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

# D3D12DDI_HEAP_FLAGS enumeration



## -description
Contains Direct3D 12 heap flags. 



## -syntax

````
typedef enum D3D12DDI_HEAP_FLAGS { 
  D3D12DDI_HEAP_FLAG_NONE                 = 0x0,
  D3D12DDI_HEAP_FLAG_NON_RT_DS_TEXTURES   = 0x2,
  D3D12DDI_HEAP_FLAG_BUFFERS              = 0x4,
  D3D12DDI_HEAP_FLAG_COHERENT_SYSTEMWIDE  = 0x8,
  D3D12DDI_HEAP_FLAG_PRIMARY              = 0x10,
  D3D12DDI_HEAP_FLAG_RT_DS_TEXTURES       = 0x20,
  D3D12DDI_HEAP_FLAG_CONTENT_PROTECTION   = 0x40
} D3D12DDI_HEAP_FLAGS;
````


## -enum-fields

### -field D3D12DDI_HEAP_FLAG_NONE

No flags.


### -field D3D12DDI_HEAP_FLAG_NON_RT_DS_TEXTURES

The heap supports resources allocated for other than Render Target (RT) and Depth-Stencil (DS) textures. 


### -field D3D12DDI_HEAP_FLAG_BUFFERS

The heap supports resources allocated for buffers.


### -field D3D12DDI_HEAP_FLAG_COHERENT_SYSTEMWIDE

The heap supports resources allocated for coherent systemwide. 


### -field D3D12DDI_HEAP_FLAG_PRIMARY

The heap supports resources allocated for primary.


### -field D3D12DDI_HEAP_FLAG_RT_DS_TEXTURES

The heap supports resources allocated for RT and DS textures.


### -field D3D12DDI_HEAP_FLAG_CONTENT_PROTECTION 

The heap supports resources allocated for content protection.


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