---
UID : NC:d3d12umddi.PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021
title : PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021
author : windows-driver-content
description : The pfnProcessorTrimAllocations callback function trims allocations for submissions that are finished.
old-location : display\pfnd3d12ddi_video_processor_trim_allocations.htm
old-project : display
ms.assetid : 505B3502-FC2D-47FB-B8CD-3D7DE9ED4770
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.pfnd3d12ddi_video_processor_trim_allocations, pfnProcessorTrimAllocations callback function [Display Devices], pfnProcessorTrimAllocations, PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021, PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021, d3d12umddi/pfnProcessorTrimAllocations
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d12umddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3D11_1DDI_GETCAPTUREHANDLEDATA
---


# PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021 callback function
The <i>pfnProcessorTrimAllocations</i> callback function  trims allocations for submissions that are finished.

## Syntax

```
PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021 Pfnd3d12ddiVideoProcessorTrimAllocations0021;

UINT64 Pfnd3d12ddiVideoProcessorTrimAllocations0021(
  D3D12DDI_HDEVICE hdrvDevice,
  D3D12DDI_HVIDEOPROCESSOR_0020 hDrvVideoProcessor,
  UINT64 SubmissionID
)
{...}
```

## Parameters

`hdrvDevice`



`hDrvVideoProcessor`

The video processor for which to submit this frame.

`SubmissionID`

The submission ID is a monotonically increasing integer value.  The value passed to this method indicates that the submission ID and all earlier values are now complete and the driver may free or re-use resources associated with this ID.


## Return Value

None

## Remarks

Applications track command completion.  To allow driver to manage memory, an application calls this method with a <i>SubmissionID</i> parameter to indicate which submissions are complete.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | d3d12umddi.h |