---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033
title: PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033
author: windows-driver-content
description: Used to calculate the size of a video decoder heap.
old-location: display\pfnd3d12ddi_calcprivatevideodecoderheapsize_0033.htm
old-project: display
ms.assetid: 4E635513-690F-4C23-8B2B-1B5FCAFE7F07
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3d12ddi_calcprivatevideodecoderheapsize_0033, PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033 entry point [Display Devices], PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033, d3d12umddi/PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d12umddi.h
apiname:
-	PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---


# PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033 callback function
Used to calculate the size of a video decoder heap.

## Syntax

```
PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033 Pfnd3d12ddiCalcprivatevideodecoderheapsize0033;

SIZE_T Pfnd3d12ddiCalcprivatevideodecoderheapsize0033(
  D3D12DDI_HDEVICE hDrvDevice,
  CONST D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033 *pArgs
)
{...}
```

## Parameters

`hDrvDevice`

The hardware device being processed.

`*pArgs`

The arguments used to create a video decoder heap.


## Return Value

Returns the size of the heap in bytes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | d3d12umddi.h |