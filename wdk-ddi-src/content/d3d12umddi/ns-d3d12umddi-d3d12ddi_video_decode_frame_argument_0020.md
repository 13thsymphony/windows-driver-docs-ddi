---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020
title: D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020
author: windows-driver-content
description: Contains the decode parameters for the frame.
old-location: display\d3d12ddi_video_decode_frame_parameter.htm
old-project: display
ms.assetid: 5651BDA8-256F-4041-A8BB-E3B30DB1870C
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020, D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020, display.d3d12ddi_video_decode_frame_parameter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020
---

# D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020 structure
Contains the decode parameters for the frame.

## Syntax
````
typedef struct D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020 {
  D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020 Type;
  VOID                                      *pData;
  UINT                                      Size;
} D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020;
````

## Members


`Type`

The type of the parameter.  For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_parameter_type_0020.md">D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE</a> enumeration.

`pData`

A pointer to the parameter data.

`Size`

The size, in bytes, of the parameter data specified by the <i>pParameter</i> parameter.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_parameter_type_0020.md">D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE</a>