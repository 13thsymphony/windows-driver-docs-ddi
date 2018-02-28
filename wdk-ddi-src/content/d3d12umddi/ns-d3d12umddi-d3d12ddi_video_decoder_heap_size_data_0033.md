---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033
title: D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033
author: windows-driver-content
description: The video decoder heap size data.
old-location: display\d3d12ddi-video-decoder-heap-size-data-0033.htm
old-project: display
ms.assetid: beec0f3e-f87b-408b-8745-14b556254d77
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033, D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033, display.d3d12ddi-video-decoder-heap-size-data-0033
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
-	d3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033
---

# D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033 structure
The video decoder heap size data.

## Syntax
````
typedef struct _D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033 {
  D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033  VideoDecoderHeapDesc;
  UINT64                                      MemoryPoolL0Size;
  UINT64                                      MemoryPoolL1Size;
} D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033, D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033;
````

## Members


`MemoryPoolL0Size`

The memory pool L0 size.

`MemoryPoolL1Size`

The memory pool L1 size.

`VideoDecoderHeapDesc`

The video decoder heap description.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |