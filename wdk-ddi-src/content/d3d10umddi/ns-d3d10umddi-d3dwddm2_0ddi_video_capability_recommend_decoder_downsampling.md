---
UID : NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING
title : D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING
author : windows-driver-content
description : D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING is used by the user-mode driver to recommend downsampling parameters that can be used to decode the stream in real-time.
old-location : display\d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling.htm
old-project : display
ms.assetid : 5BC38128-8866-48C9-B5C5-4D6B6DB793E0
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING, D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING
req.alt-loc : D3d10umddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING
---

# D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING structure
<b>D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING</b> is used by the user-mode driver to recommend downsampling parameters that can be used to decode the stream in real-time.

## Syntax
````
typedef struct D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING {
  const D3D11_1DDI_VIDEO_DECODER_DESC   *pInputDesc;
  D3DDDI_COLOR_SPACE_TYPE               InputColorSpace;
  const D3D11_1DDI_VIDEO_DECODER_CONFIG *pInputConfig;
  const DXGI_RATIONAL                   *pFrameRate;
  D3D11_1DDI_VIDEO_DECODER_DESC         *pOutputDesc;
  D3DDDI_COLOR_SPACE_TYPE               OutputColorSpace;
} D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING;
````

## Members

        
            `InputColorSpace`

            Contains the color space information of the reference frame data.
        
            `OutputColorSpace`

            The driver returns the recommended color space information of the display frame data.
        
            `pFrameRate`

            Contains the frame rate of the video content.
        
            `pInputConfig`

            Contains the configuration data associated with the decode profile.
        
            `pInputDesc`

            Contains the decode profile used and the resolution and format of the reference frames.  This is the resolution/format to be downsampled (e.g. 4K, DXGI_FORMAT_P010).
        
            `pOutputDesc`

            The driver returns the recommended resolution and the format of the output/display frames.  



<div class="alert"><b>Note</b>  The decode profile (<b>Guid</b>) member of <b>pOutputDesc</b> can be ignored.
</div>
<div> </div>

    ## Remarks
        The driver recommends the down sample parameters such that the video stream can be decoded in real-time. If no down sample solution exists that can result in real-time decode, the driver should recommend the configuration that is closest to the real-time solution. </p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |