---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0030
title: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0030
author: windows-driver-content
description: Video decode input stream arguments.
old-location: display\d3d12ddi-video-decode-input-stream-arguments-0030.htm
old-project: display
ms.assetid: 186115c0-14ed-4ca0-9f47-fdcf8f0b586c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0030, D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0030 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0030, display.d3d12ddi-video-decode-input-stream-arguments-0030
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
-	D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0030
---

# D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0030 structure
Video decode input stream arguments.

## Syntax
```
typedef struct D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0030 {
  D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020       FrameArguments[D3D12DDI_VIDEO_DECODE_MAX_ARGUMENTS_0020];
  UINT                                            FrameArgumentsCount;
  D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0020     ReferenceFrames;
  D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020 CompressedBitstream;
  D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030 DecryptionParameters;
};
```

## Members


`FrameArguments`

Frame arguments.

`FrameArgumentsCount`

Frame arguments count.

`ReferenceFrames`

Reference frames.

`CompressedBitstream`

Compressed bitstream.

`DecryptionParameters`

Decryption parameters.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |