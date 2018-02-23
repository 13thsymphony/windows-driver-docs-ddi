---
UID: NE:d3d12umddi.D3D12DDI_RESOURCE_STATES
title: D3D12DDI_RESOURCE_STATES
author: windows-driver-content
description: Contains resource states.
old-location: display\d3d12ddi_resource_states.htm
old-project: display
ms.assetid: E5DB8AF3-A6ED-4CD7-9723-78ACD57F1723
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.d3d12ddi_resource_states, D3D12DDI_RESOURCE_STATE_UNORDERED_ACCESS, D3D12DDI_RESOURCE_STATE_RESOLVE_SOURCE, D3D12DDI_RESOURCE_STATE_VERTEX_AND_CONSTANT_BUFFER, D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_READ, D3D12DDI_RESOURCE_STATE_PIXEL_SHADER_RESOURCE, d3d12umddi/D3D12DDI_RESOURCE_STATE_DEPTH_WRITE, D3D12DDI_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE, d3d12umddi/D3D12DDI_RESOURCE_STATE_COMMON, D3D12DDI_RESOURCE_STATE_DEPTH_WRITE, d3d12umddi/D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_WRITE, D3D12DDI_RESOURCE_STATE_RENDER_TARGET, D3D12DDI_RESOURCE_STATE_STREAM_OUT, d3d12umddi/D3D12DDI_RESOURCE_STATE_UNORDERED_ACCESS, D3D12DDI_RESOURCE_STATE_COPY_SOURCE, D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_WRITE, d3d12umddi/D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_WRITE, d3d12umddi/D3D12DDI_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE, d3d12umddi/D3D12DDI_RESOURCE_STATE_INDEX_BUFFER, D3D12DDI_RESOURCE_STATES enumeration [Display Devices], d3d12umddi/D3D12DDI_RESOURCE_STATE_PIXEL_SHADER_RESOURCE, d3d12umddi/D3D12DDI_RESOURCE_STATES, d3d12umddi/D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_READ, d3d12umddi/D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_READ, D3D12DDI_RESOURCE_STATE_COPY_DEST, D3D12DDI_RESOURCE_STATE_DEPTH_READ, D3D12DDI_RESOURCE_STATE_INDEX_BUFFER, D3D12DDI_RESOURCE_STATES, D3D12DDI_RESOURCE_STATE_RESOLVE_DEST, d3d12umddi/D3D12DDI_RESOURCE_STATE_VERTEX_AND_CONSTANT_BUFFER, D3D12DDI_RESOURCE_STATE_COMMON, d3d12umddi/D3D12DDI_RESOURCE_STATE_DEPTH_READ, d3d12umddi/D3D12DDI_RESOURCE_STATE_COPY_DEST, D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_READ, d3d12umddi/D3D12DDI_RESOURCE_STATE_RESOLVE_SOURCE, d3d12umddi/D3D12DDI_RESOURCE_STATE_COPY_SOURCE, D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_WRITE, d3d12umddi/D3D12DDI_RESOURCE_STATE_RENDER_TARGET, D3D12DDI_RESOURCE_STATE_INDIRECT_ARGUMENT, d3d12umddi/D3D12DDI_RESOURCE_STATE_INDIRECT_ARGUMENT, d3d12umddi/D3D12DDI_RESOURCE_STATE_STREAM_OUT, d3d12umddi/D3D12DDI_RESOURCE_STATE_RESOLVE_DEST
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
-	D3D12DDI_RESOURCE_STATES
product: Windows
targetos: Windows
req.typenames: D3D12DDI_RESOURCE_STATES
---

# D3D12DDI_RESOURCE_STATES Enumeration
Contains resource states.

## Syntax
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

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_READ</td>
                    <td>Video decode read.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_0020_VIDEO_DECODE_WRITE</td>
                    <td>Video decode write.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_READ</td>
                    <td>Video process read.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_0020_VIDEO_PROCESS_WRITE</td>
                    <td>Video process write.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_COMMON</td>
                    <td>Common.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_COPY_DEST</td>
                    <td>Copy destination.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_COPY_SOURCE</td>
                    <td>Copy source.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_DEPTH_READ</td>
                    <td>Depth read.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_DEPTH_WRITE</td>
                    <td>Depth write.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_INDEX_BUFFER</td>
                    <td>Index buffer.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_INDIRECT_ARGUMENT</td>
                    <td>Indirect argument.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE</td>
                    <td>Non-pixel shader resource.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_PIXEL_SHADER_RESOURCE</td>
                    <td>Pixel shader retsource.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_RENDER_TARGET</td>
                    <td>Render target.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_RESOLVE_DEST</td>
                    <td>Resolve destination.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_RESOLVE_SOURCE</td>
                    <td>Resolve source.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_STREAM_OUT</td>
                    <td>Stream out.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_UNORDERED_ACCESS</td>
                    <td>Unordered access.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_RESOURCE_STATE_VERTEX_AND_CONSTANT_BUFFER</td>
                    <td>Vertex and constant buffer.</td>
                </tr>
</table>

## Remarks

Resource barriers allow transitioning between hardware specific states for a corresponding operation and to synchronize read after write.  

Resource barriers are an existing concept in D3D12 that is extended to support video decode by adding new usage flags.
The write state is used for the decode target.  The write state is also used when decode conversion is enabled for the non-converted reference.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |