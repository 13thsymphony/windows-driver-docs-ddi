---
UID : NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0032
title : D3D12DDI_DEVICE_FUNCS_VIDEO_0032
author : windows-driver-content
description : Video device functions.
old-location : display\d3d12ddi-device-funcs-video-0032.htm
old-project : display
ms.assetid : 2b71c48a-a028-4bfa-a8bd-ad612aa800ff
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_DEVICE_FUNCS_VIDEO_0032, D3D12DDI_DEVICE_FUNCS_VIDEO_0032
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d12umddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3D12DDI_DEVICE_FUNCS_VIDEO_0032
req.alt-loc : d3d12umddi.h
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
req.typenames : D3D12DDI_DEVICE_FUNCS_VIDEO_0032
---

# D3D12DDI_DEVICE_FUNCS_VIDEO_0032 structure
Video device functions.

## Syntax
````
typedef struct _D3D12DDI_DEVICE_FUNCS_VIDEO_0032 {
  PFND3D12DDI_VIDEO_GETCAPS                         pfnGetCaps;
  PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0032      pfnCalcPrivateVideoDecoderSize;
  PFND3D12DDI_CREATEVIDEODECODER_0032               pfnCreateVideoDecoder;
  PFND3D12DDI_DESTROYVIDEODECODER_0021              pfnDestroyVideoDecoder;
  PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0032  pfnCalcPrivateVideoDecoderHeapSize;
  PFND3D12DDI_CREATEVIDEODECODERHEAP_0032           pfnCreateVideoDecoderHeap;
  PFND3D12DDI_DESTROYVIDEODECODERHEAP_0032          pfnDestroyVideoDecoderHeap;
  PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032    pfnCalcPrivateVideoProcessorSize;
  PFND3D12DDI_CREATEVIDEOPROCESSOR_0032             pfnCreateVideoProcessor;
  PFND3D12DDI_DESTROYVIDEOPROCESSOR_0021            pfnDestroyVideoProcessor;
} D3D12DDI_DEVICE_FUNCS_VIDEO_0032, D3D12DDI_DEVICE_FUNCS_VIDEO_0032;
````

## Members

        
            `pfnCalcPrivateVideoDecoderHeapSize`

            Calculate private video decoder heap size.
        
            `pfnCalcPrivateVideoDecoderSize`

            Calculate private video decoder size.
        
            `pfnCalcPrivateVideoProcessorSize`

            Calculate private video processor size.
        
            `pfnCreateVideoDecoder`

            Create video decoder.
        
            `pfnCreateVideoDecoderHeap`

            Create video decoder heap.
        
            `pfnCreateVideoProcessor`

            Create video processor.
        
            `pfnDestroyVideoDecoder`

            Destroy video decoder.
        
            `pfnDestroyVideoDecoderHeap`

            Destroy video decoder heap.
        
            `pfnDestroyVideoProcessor`

            Destroy video processor.
        
            `pfnGetCaps`

            Get caps.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d12umddi.h |