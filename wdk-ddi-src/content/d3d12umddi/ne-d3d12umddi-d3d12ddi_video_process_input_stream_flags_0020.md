---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020
title: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020
author: windows-driver-content
description: Input stream flags.
old-location: display\d3d12ddi_video_process_input_stream_flags.htm
old-project: display
ms.assetid: 6BF1C31E-45F8-4921-87A2-53331530EAC4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020
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
req.alt-api: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020
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
req.typenames: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020
---

# D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020 enumeration



## -description
Input stream flags.



## -syntax

````
typedef enum D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020 { 
  D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_NONE                 = 0x0,
  D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_FRAME_DISCONTINUITY  = 0x1,
  D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_FRAME_REPEAT         = 0x2
} D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020;
````


## -enum-fields

### -field D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_NONE

No flags specified.


### -field D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_FRAME_DISCONTINUITY

The application must set this flag when not processing frames in order, such as seeking between frames.  This should be a hint that cached filter processing from previous calls to process frames is invalid.


### -field D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_FRAME_REPEAT

The application must set this flag when it applies video process operations to the same set of inputs.  For example, paused video where the window is being resized causing a scale.


## -remarks
