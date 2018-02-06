---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032
title: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032
author: windows-driver-content
description: Video decode conversion support data.
old-location: display\d3d12ddi-video-decode-conversion-support-data-0032.htm
old-project: display
ms.assetid: 1395fe30-9bbf-433c-8696-a0f842bad10e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032, D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032 structure [Display Devices], display.d3d12ddi-video-decode-conversion-support-data-0032, d3d12umddi/D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032
---

# D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032 structure
Video decode conversion support data.

## Syntax
````
typedef struct _D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032 {
  UINT                                                 NodeIndex;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020             Configuration;
  D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020               DecodeSample;
  D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020               OutputFormat;
  DXGI_RATIONAL                                        FrameRate;
  UINT                                                 BitRate;
  D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS_0020  SupportFlags;
  D3D12DDI_VIDEO_SCALE_SUPPORT_0032                    ScaleSupport;
} D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032, D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032;
````

## Members


`BitRate`

Bitrate.

`Configuration`

Configuration.

`DecodeSample`

Decode sample.

`FrameRate`

Frame rate.

`NodeIndex`

Node index.

`OutputFormat`

Output format.

`ScaleSupport`

Scale support.

`SupportFlags`

Support flags.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |