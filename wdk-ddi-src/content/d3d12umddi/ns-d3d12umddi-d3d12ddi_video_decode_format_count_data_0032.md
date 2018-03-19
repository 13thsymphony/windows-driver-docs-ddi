---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
title: D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
author: windows-driver-content
description: Video decode format count data.
old-location: display\d3d12ddi-video-decode-format-count-data-0032.htm
old-project: display
ms.assetid: 3d28fe10-1dfc-4017-9ab0-d8b8e2d45448
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032, D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032, display.d3d12ddi-video-decode-format-count-data-0032
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
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
-	d3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
---

# D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032 structure
Video decode format count data.

## Syntax
````
typedef struct _D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032 {
  UINT                                      NodeIndex;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020  Configuration;
  UINT                                      FormatCount;
} D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032, D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032;
````

## Members


`NodeIndex`

Node index.

`Configuration`

Configuration.

`FormatCount`

Format count.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |