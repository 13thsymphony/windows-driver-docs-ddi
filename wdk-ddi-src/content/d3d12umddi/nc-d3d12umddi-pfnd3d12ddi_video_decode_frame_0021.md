---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_DECODE_FRAME_0021
title: PFND3D12DDI_VIDEO_DECODE_FRAME_0021
author: windows-driver-content
description: The pfnDecodeFrame callback function records a decode frame operation to the command list.
old-location: display\pfnd3d12ddi_video_decode_frame.htm
old-project: display
ms.assetid: 8EA34C58-9B2D-4B69-ABAB-D67F6BCD6229
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D12DDI_VIDEO_DECODE_FRAME_0021, d3d12umddi/pfnDecodeFrame, display.pfnd3d12ddi_video_decode_frame, pfnDecodeFrame, pfnDecodeFrame callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnDecodeFrame
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---


# PFND3D12DDI_VIDEO_DECODE_FRAME_0021 callback function
The <i>pfnDecodeFrame</i> callback function records a decode frame operation to the command list.

## Syntax

```
PFND3D12DDI_VIDEO_DECODE_FRAME_0021 Pfnd3d12ddiVideoDecodeFrame0021;

void Pfnd3d12ddiVideoDecodeFrame0021(
  D3D12DDI_HCOMMANDLIST hDrvCommandList,
  D3D12DDI_HVIDEODECODER_0020 hDrvDecoder,
  UINT64 SubmissionID,
  const D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0021 *pOutputStreamParameters,
  const D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020 *pInputStreamParameters
)
{...}
```

## Parameters

`hDrvCommandList`

The command list used to record this process frames command.

`hDrvDecoder`

The video decoder that contains internal state for this decode session.  Examples include motion vectors and internal temporary allocations.

`SubmissionID`

The submission ID is a monotonically increasing integer value.  The value passed to this function must be larger than any passed decode frame submission for the decoder specified by the <i>hDrvVideoDecoder</i> parameter.  Callers should use fences to track submission completion and then provide completed submission IDs to drivers by using <a href="https://msdn.microsoft.com/2E90B365-8C5D-4586-AAA8-D49CC9BBCF70">pfnDecoderTrimAllocations</a> to allow driver to manage resources associated with that decoder.

`*pOutputStreamParameters`



`*pInputStreamParameters`




## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | d3d12umddi.h |

## See Also

<a href="https://msdn.microsoft.com/B956626C-B5D7-4217-A90A-EC7E436DF6C0">D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS</a>



<a href="https://msdn.microsoft.com/4179447D-481F-4EC3-922C-4DFE3F5D768F">D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS</a>



<a href="https://msdn.microsoft.com/2E90B365-8C5D-4586-AAA8-D49CC9BBCF70">pfnDecoderTrimAllocations</a>