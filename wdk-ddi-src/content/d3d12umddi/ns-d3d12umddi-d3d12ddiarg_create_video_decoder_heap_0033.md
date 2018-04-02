---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033
title: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033
author: windows-driver-content
description: Create a video decoder heap.
old-location: display\d3d12ddiarg-create-video-decoder-heap-0033.htm
old-project: display
ms.assetid: 158411ee-6cc1-466d-b772-fe380b55baef
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033, D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033 structure [Display Devices], d3d12umddi/D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033, display.d3d12ddiarg-create-video-decoder-heap-0033
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
-	D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033
product:
- Windows
targetos: Windows
req.typenames: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033
---

# D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033 structure
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Create a video decoder heap.

## Syntax
```
typedef struct D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033 {
  UINT                                     NodeMask;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020 Configuration;
  UINT                                     DecodeWidth;
  UINT                                     DecodeHeight;
  DXGI_FORMAT                              Format;
  DXGI_RATIONAL                            FrameRate;
  UINT                                     BitRate;
  UINT                                     MaxDecodePictureBufferCount;
};
```

## Members


`NodeMask`

The set of nodes.

`Configuration`

The video decode configuration.

`DecodeWidth`

Decode width.

`DecodeHeight`

Decode height.

`Format`

The resource data format.

`FrameRate`

A rational number that specifies the frame rate.

`BitRate`

The number of bits per second.

`MaxDecodePictureBufferCount`

Maximum decode picture buffer count.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |