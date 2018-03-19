---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021
title: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021
author: windows-driver-content
description: Specifies arguments used to create a video processor.
old-location: display\d3d12ddiarg_create_video_processor.htm
old-project: display
ms.assetid: 2FA77D7D-E1CC-44BA-8725-7132682A1BD6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021, D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021 structure [Display Devices], d3d12umddi/D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021, display.d3d12ddiarg_create_video_processor
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
-	D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021
product: Windows
targetos: Windows
req.typenames: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021
---

# D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021 structure
Specifies arguments used to create a video processor.

## Syntax
````
typedef struct D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021 {
  UINT                 NodeMask;
  D3D12DDI_VIDEO_USAGE Usage;
} D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021;
````

## Members


`NodeMask`

A node mask. For single GPU operation, set this value to zero (0). If there are multiple GPU nodes, set a bit to identify the physical adapter of the device to which the command queue applies. Each bit in the mask corresponds to a single node. Only one  bit may be set.

`Usage`

Specifies a hint for the intended usage for the video processor. For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_usage.md">D3D12DDI_VIDEO_USAGE</a> enumeration.

## Remarks
A video processor holds state for a video processing session. State includes required intermediate memory, cached processing data, or other temporary working space.  A separate video processor must be created for each content stream by the application.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_usage.md">D3D12DDI_VIDEO_USAGE</a>