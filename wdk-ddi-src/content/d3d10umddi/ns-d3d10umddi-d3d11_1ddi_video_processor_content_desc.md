---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC
title: D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC
author: windows-driver-content
description: Describes a video stream for a video processor.
old-location: display\d3d11_1ddi_video_processor_content_desc.htm
old-project: display
ms.assetid: f624ffc4-3313-46a3-9231-15a54c3f2791
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC, D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC, display.d3d11_1ddi_video_processor_content_desc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC
---

# D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC structure
Describes a video stream for a video processor.

## Syntax
```
typedef struct D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC {
  D3D11_1DDI_VIDEO_FRAME_FORMAT InputFrameFormat;
  DXGI_RATIONAL                 InputFrameRate;
  UINT                          InputWidth;
  UINT                          InputHeight;
  DXGI_RATIONAL                 OutputFrameRate;
  UINT                          OutputWidth;
  UINT                          OutputHeight;
  D3D11_1DDI_VIDEO_USAGE        Usage;
};
```

## Members


`InputFrameFormat`

A member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450954">D3D11_1DDI_VIDEO_FRAME_FORMAT</a> enumeration that describes how the video stream is interlaced.

`InputFrameRate`

The frame rate of the input video stream, specified as a <a href="https://msdn.microsoft.com/0a878d11-dc90-4cad-bde5-54a135e53a86">DXGI_RATIONAL</a> structure.

`InputWidth`

The width of the input frames, in pixels.

`InputHeight`

The height of the input frames, in pixels.

`OutputFrameRate`

The frame rate of the output video stream, specified as a <a href="https://msdn.microsoft.com/0a878d11-dc90-4cad-bde5-54a135e53a86">DXGI_RATIONAL</a> structure.

`OutputWidth`

The width of the output frames, in pixels.

`OutputHeight`

The height of the output frames, in pixels.

`Usage`

A member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451037">D3D11_1DDI_VIDEO_USAGE</a> enumeration that describes how the video processor will be used. The value indicates the desired trade-off between speed and video quality. The driver uses this flag as a hint when it creates the video processor.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450954">D3D11_1DDI_VIDEO_FRAME_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451037">D3D11_1DDI_VIDEO_USAGE</a>



<a href="https://msdn.microsoft.com/0a878d11-dc90-4cad-bde5-54a135e53a86">DXGI_RATIONAL</a>