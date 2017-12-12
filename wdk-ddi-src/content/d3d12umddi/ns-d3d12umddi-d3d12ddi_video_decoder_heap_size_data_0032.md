---
UID: NS.D3D12UMDDI.D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0032
title: D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0032
author: windows-driver-content
description: Data structure for the D3D12DDICAPS_TYPE_VIDEO_0032_DECODER_HEAP_SIZE capability check. Retrieves the memory allocation size of a video decoder heap created with the given properties.
old-location: display\d3d12ddi_video_decoder_heap_size_data_0032.htm
old-project: display
ms.assetid: 5EF65599-65C3-4EA8-A3A7-3849CF01DE87
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0032, D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0032
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0032
req.alt-loc: d3d12umddi.h
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

# D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0032 structure



## -description
Data structure for the D3D12DDICAPS_TYPE_VIDEO_0032_DECODER_HEAP_SIZE capability check.  Retrieves the memory allocation size of a video decoder heap created with the given properties.



## -syntax

````
typedef struct _D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0032 {
  D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032 VideoDecoderHeapDesc;
  UINT64                                     MemoryPoolL0Size;
  UINT64                                     MemoryPoolL1Size;
} D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0032;
````


## -struct-fields

### -field VideoDecoderHeapDesc

The creation properties for a video decoder heap.  Driver should map these creation properties to size.


### -field MemoryPoolL0Size

The L0 size of the heap object.  Memory Pool L0 is the memory pool “closest” to the GPU.  In the case of UMA adapters, this is the amount of system memory used.  For discrete adapters, this is the amount of discrete memory used.


### -field MemoryPoolL1Size

The L1 size of the heap object.  Memory Pool L1 is the memory pool “second closest” to the GPU.  In the case of UMA adapters, this value is zero.  In the case of discrete adapters, this is the amount of system memory used.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>