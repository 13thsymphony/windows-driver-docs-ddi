---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
title: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
author: windows-driver-content
description: Contains stream information for the video processor blend functionality.
old-location: display\d3d12ddi_video_process_input_stream.htm
old-project: display
ms.assetid: DB0AF7A5-8E90-45B8-AF9C-58BFF7CE066E
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020, display.d3d12ddi_video_process_input_stream
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
-	D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
---

# D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020 structure
Contains stream information for the video processor blend functionality.

## Syntax
````
typedef struct D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020 {
  D3D12DDI_HRESOURCE                          hDrvInputTexture;
  UINT                                        Subresource;
  D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020 ReferenceInfo;
} D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020;
````

## Members


`hDrvInputTexture`

The current input field or frame.

`ReferenceInfo`

The set of references to be able to perform processing.

`Subresource`

The subresource index to use of the <i>hDrvInputTexture</i> argument.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |