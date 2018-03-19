---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032
title: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032
author: windows-driver-content
description: Video decode input stream arguments.
old-location: display\d3d12ddi-video-decode-input-stream-arguments-0032.htm
old-project: display
ms.assetid: ca647cd3-357b-4cd6-aa1c-6a03d5a77f10
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032, D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032, display.d3d12ddi-video-decode-input-stream-arguments-0032
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
-	D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032
---

# D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032 structure
Video decode input stream arguments.

## Syntax
````
typedef struct _D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032 {
  D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020 [D3D12DDI_VIDEO_DECODE_MAX_ARGUMENTS_0020] FrameArguments;
  UINT                                                                                 NumFrameArguments;
  D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032                                          ReferenceFrames;
  D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0032                                      CompressedBitstream;
  D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030                                      DecryptionParameters;
  D3D12DDI_HVIDEODECODERHEAP_0032                                                      hDrvVideoDecoderHeap;
} D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032, D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032;
````

## Members


`FrameArguments`

Frame arguments.

`NumFrameArguments`

The number of frame arguments.

`ReferenceFrames`

Reference frames.

`CompressedBitstream`

Compressed bitstream.

`DecryptionParameters`

Decryption parameters.

`hDrvVideoDecoderHeap`

Video decoder heap.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |