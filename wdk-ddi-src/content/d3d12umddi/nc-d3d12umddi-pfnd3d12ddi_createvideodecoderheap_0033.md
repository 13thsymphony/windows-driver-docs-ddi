---
UID : NC:d3d12umddi.PFND3D12DDI_CREATEVIDEODECODERHEAP_0033
title : PFND3D12DDI_CREATEVIDEODECODERHEAP_0033
author : windows-driver-content
description : Used to create a video decoder heap.
old-location : display\pfnd3d12ddi_createvideodecoderheap_0033_.htm
old-project : display
ms.assetid : BCCDBC42-FE6B-49C6-9E95-F0CF7F5CCB2E
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.pfnd3d12ddi_createvideodecoderheap_0033_, PFND3D12DDI_CREATEVIDEODECODERHEAP_0033 callback function [Display Devices], PFND3D12DDI_CREATEVIDEODECODERHEAP_0033, d3d12umddi/PFND3D12DDI_CREATEVIDEODECODERHEAP_0033
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d12umddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
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


# PFND3D12DDI_CREATEVIDEODECODERHEAP_0033 callback function
Used to create a video decoder heap.

## Syntax

```
PFND3D12DDI_CREATEVIDEODECODERHEAP_0033 Pfnd3d12ddiCreatevideodecoderheap0033;

HRESULT Pfnd3d12ddiCreatevideodecoderheap0033(
  D3D12DDI_HDEVICE hDrvDevice,
  CONST D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033 *,
  D3D12DDI_HVIDEODECODERHEAP_0032 hDrvVideoDecoderHeap
)
{...}
```

## Parameters

`hDrvDevice`

The hardware device being processed.

`*`



`hDrvVideoDecoderHeap`

The video decoder heap.


## Return Value

Returns STATUS_SUCCESS if completed successfully.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d12umddi.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |