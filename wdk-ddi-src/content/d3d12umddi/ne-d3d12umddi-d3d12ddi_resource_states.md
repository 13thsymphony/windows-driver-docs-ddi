---
UID: NE.d3d12umddi.D3D12DDI_RESOURCE_STATES
title: D3D12DDI_RESOURCE_STATES
author: windows-driver-content
description: Contains resource states.
old-location: display\d3d12ddi_resource_states.htm
old-project: display
ms.assetid: E5DB8AF3-A6ED-4CD7-9723-78ACD57F1723
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D12DDI_RESOURCE_STATES, D3D12DDI_RESOURCE_STATES
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
req.alt-api: D3D12DDI_RESOURCE_STATES
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

# D3D12DDI_RESOURCE_STATES enumeration



## -description
Contains resource states. 



## -syntax

````
typedef enum D3D12DDI_RESOURCE_STATES { 
  D3D12DDI_RESOURCE_STATE_COMMON                      = 0x00000000,
  D3D12DDI_RESOURCE_STATE_VERTEX_AND_CONSTANT_BUFFER  = 0x00000001,
  D3D12DDI_RESOURCE_STATE_INDEX_BUFFER                = 0x00000002,
  D3D12DDI_RESOURCE_STATE_RENDER_TARGET               = 0x00000004,
  D3D12DDI_RESOURCE_STATE_UNORDERED_ACCESS            = 0x00000008,
  D3D12DDI_RESOURCE_STATE_DEPTH_WRITE                 = 0x00000010,
  D3D12DDI_RESOURCE_STATE_DEPTH_READ                  = 0x00000020,
  D3D12DDI_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE   = 0x00000040,
  D3D12DDI_RESOURCE_STATE_PIXEL_SHADER_RESOURCE       = 0x00000080,
  D3D12DDI_RESOURCE_STATE_STREAM_OUT                  = 0x00000100,
  D3D12DDI_RESOURCE_STATE_INDIRECT_ARGUMENT           = 0x00000200,
  D3D12DDI_RESOURCE_STATE_COPY_DEST                   = 0x00000400,
  D3D12DDI_RESOURCE_STATE_COPY_SOURCE                 = 0x00000800,
  D3D12DDI_RESOURCE_STATE_RESOLVE_DEST                = 0x00001000,
  D3D12DDI_RESOURCE_STATE_RESOLVE_SOURCE              = 0x00002000,
  D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_READ      = 0x00010000,
  D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_WRITE     = 0x00020000,
  D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_READ     = 0x00040000,
  D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_WRITE    = 0x00080000
} D3D12DDI_RESOURCE_STATES;
````


## -enum-fields

### -field D3D12DDI_RESOURCE_STATE_COMMON

Common. 


### -field D3D12DDI_RESOURCE_STATE_VERTEX_AND_CONSTANT_BUFFER

Vertex and constant buffer.


### -field D3D12DDI_RESOURCE_STATE_INDEX_BUFFER

Index buffer.


### -field D3D12DDI_RESOURCE_STATE_RENDER_TARGET

Render target.


### -field D3D12DDI_RESOURCE_STATE_UNORDERED_ACCESS

Unordered access.


### -field D3D12DDI_RESOURCE_STATE_DEPTH_WRITE

Depth write. 


### -field D3D12DDI_RESOURCE_STATE_DEPTH_READ

Depth read.


### -field D3D12DDI_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE

Non-pixel shader resource.


### -field D3D12DDI_RESOURCE_STATE_PIXEL_SHADER_RESOURCE

Pixel shader retsource.


### -field D3D12DDI_RESOURCE_STATE_STREAM_OUT

Stream out.


### -field D3D12DDI_RESOURCE_STATE_INDIRECT_ARGUMENT

Indirect argument.


### -field D3D12DDI_RESOURCE_STATE_COPY_DEST

Copy destination.


### -field D3D12DDI_RESOURCE_STATE_COPY_SOURCE

Copy source.


### -field D3D12DDI_RESOURCE_STATE_RESOLVE_DEST

Resolve destination. 


### -field D3D12DDI_RESOURCE_STATE_RESOLVE_SOURCE

Resolve source.


### -field D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_READ

Video decode read.


### -field D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_WRITE

Video decode write.


### -field D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_READ

Video process read.


### -field D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_WRITE

Video process write.


## -remarks
Resource barriers allow transitioning between hardware specific states for a corresponding operation and to synchronize read after write.  

Resource barriers are an existing concept in D3D12 that is extended to support video decode by adding new usage flags.
The write state is used for the decode target.  The write state is also used when decode conversion is enabled for the non-converted reference.



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