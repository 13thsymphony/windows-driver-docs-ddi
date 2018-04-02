---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020
title: D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020
author: windows-driver-content
description: Describes the width, height, format, and color space of a picture buffer.
old-location: display\d3d12ddi_video_sample_description.htm
old-project: display
ms.assetid: B9918A06-6C10-4AD7-97EC-4FA0BC5319AD
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020, D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_SAMPLE_DESCRIPTION, display.d3d12ddi_video_sample_description
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
-	D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020
---

# D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020 structure
Describes the width, height, format, and color space of a picture buffer.

## Syntax
```
typedef struct D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020 {
  UINT                                   Width;
  UINT                                   Height;
  D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020 Format;
};
```

## Members


`Width`

The width of the sample.

`Height`

The height of the sample.

`Format`

The format and color space of the sample.  For more information, see the <a href="https://msdn.microsoft.com/47C0C369-B31B-4291-A420-A1E75BA990CF">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/47C0C369-B31B-4291-A420-A1E75BA990CF">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a>