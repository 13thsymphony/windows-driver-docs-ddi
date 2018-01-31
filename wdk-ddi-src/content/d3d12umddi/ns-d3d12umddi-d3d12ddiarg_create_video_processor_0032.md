---
UID : NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032
title : D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032
author : windows-driver-content
description : Creates a video processor.
old-location : display\d3d12ddiarg-create-video-processor-0032.htm
old-project : display
ms.assetid : 6b945476-c1cf-4bf8-8273-bb3d05b90277
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032, D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032 structure [Display Devices], d3d12umddi/D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032, display.d3d12ddiarg-create-video-processor-0032
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
req.typenames : D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032
---

# D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032 structure
Creates a video processor.

## Syntax
````
typedef struct _D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032 {
  UINT                                               NodeMask;
  D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032     OutputStream;
  D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032 *  pInputStreams;
  UINT                                               NumInputStreams;
} D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032, D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032;
````

## Members


`NodeMask`

Represents the set of nodes.

`NumInputStreams`

The number of input streams.

`OutputStream`

The output stream.

`pInputStreams`

The input stream.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d12umddi.h |