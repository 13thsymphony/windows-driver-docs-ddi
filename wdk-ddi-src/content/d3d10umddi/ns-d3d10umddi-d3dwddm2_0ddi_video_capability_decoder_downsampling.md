---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING
title: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING
author: windows-driver-content
description: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING describes the details of a video decoder downsampling operation.
old-location: display\d3dwddm2_0ddi_video_capability_decoder_downsampling.htm
old-project: display
ms.assetid: 8D12F2AC-2A64-4FEF-813C-15899FBCA108
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING, D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING, display.d3dwddm2_0ddi_video_capability_decoder_downsampling
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING
product:
- Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING
---

# D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING structure
<b>D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING</b> describes the details of a video decoder downsampling operation.

## Syntax
```
typedef struct D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING {
  CONST D3D11_1DDI_VIDEO_DECODER_DESC   *pInputDesc;
  D3DDDI_COLOR_SPACE_TYPE               InputColorSpace;
  CONST D3D11_1DDI_VIDEO_DECODER_CONFIG *pInputConfig;
  CONST DXGI_RATIONAL                   *pFrameRate;
  CONST D3D11_1DDI_VIDEO_DECODER_DESC   *pOutputDesc;
  D3DDDI_COLOR_SPACE_TYPE               OutputColorSpace;
  BOOL                                  Supported;
  BOOL                                  RealTime;
};
```

## Members


`pInputDesc`

[in] Contains the decode profile used and the resolution and format of the reference frames.  This is the resolution/format to be downsampled (e.g. 4K, DXGI_FORMAT_P010).

`InputColorSpace`

[in] Contains the color space information of the reference frame data.

`pInputConfig`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/hh450947">D3D11_1DDI_VIDEO_DECODER_CONFIG</a> structure that contains the configuration data associated with the decode profile .

`pFrameRate`

[in] Contains the frame rate of the video content.

`pOutputDesc`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/hh450951">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that contains the resolution and the format of the display frames.  This is the destination resolution and format of the down sample operation.



<div class="alert"><b>Note</b>  The decode profile (<b>Guid</b>) member of <b>pOutputDesc</b> can be ignored.
</div>
<div> </div>

`OutputColorSpace`

[in] Contains the color space information of the display frame data.

`Supported`

[out] The driver sets this to <b>TRUE</b> if the requested down sampling is supported.  Otherwise, the driver should set this to <b>FALSE</b>.

`RealTime`

[out] The driver sets this to <b>TRUE</b> if the requested down sampling is supported and the resulting decode operations can occur in real-time.  Otherwise, the driver should set this to <b>FALSE</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450947">D3D11_1DDI_VIDEO_DECODER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450951">D3D11_1DDI_VIDEO_DECODER_DESC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906320">D3DDDI_COLOR_SPACE_TYPE</a>