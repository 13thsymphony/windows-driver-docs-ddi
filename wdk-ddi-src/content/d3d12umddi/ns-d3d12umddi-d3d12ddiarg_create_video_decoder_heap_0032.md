---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032
title: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032
author: windows-driver-content
description: Creates a video decoder heap.
old-location: display\d3d12ddiarg-create-video-decoder-heap-0032.htm
old-project: display
ms.assetid: 86f8021d-9b02-457f-9bee-4631c711094f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032, D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032 structure [Display Devices], d3d12umddi/D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032, display.d3d12ddiarg-create-video-decoder-heap-0032
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
-	D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032
product:
- Windows
targetos: Windows
req.typenames: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032
---

# D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032 structure
Creates a video decoder heap.

## Syntax
```
typedef struct D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032 {
  UINT                                     NodeMask;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020 Configuration;
  UINT                                     DecodeWidth;
  UINT                                     DecodeHeight;
  UINT                                     MaxDecodePictureBufferCount;
  DXGI_RATIONAL                            FrameRate;
  UINT                                     BitRate;
};
```

## Members


`NodeMask`

Represents the set of nodes.

`Configuration`

The video decode configuration.

`DecodeWidth`

The decode width.

`DecodeHeight`

The decode height.

`MaxDecodePictureBufferCount`

The max decode picture buffer count.

`FrameRate`

The frame rate.

`BitRate`

The bitrate.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |