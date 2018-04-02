---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_SIZE_RANGE_0032
title: D3D12DDI_VIDEO_SIZE_RANGE_0032
author: windows-driver-content
description: Video size range.
old-location: display\d3d12ddi-video-size-range-0032.htm
old-project: display
ms.assetid: a4781fea-4efc-442d-8503-12be17afa9b1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_VIDEO_SIZE_RANGE_0032, D3D12DDI_VIDEO_SIZE_RANGE_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_SIZE_RANGE_0032, display.d3d12ddi-video-size-range-0032
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
-	D3D12DDI_VIDEO_SIZE_RANGE_0032
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_SIZE_RANGE_0032
---

# D3D12DDI_VIDEO_SIZE_RANGE_0032 structure
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Video size range.

## Syntax
```
typedef struct D3D12DDI_VIDEO_SIZE_RANGE_0032 {
  UINT MaxWidth;
  UINT MaxHeight;
  UINT MinWidth;
  UINT MinHeight;
};
```

## Members


`MaxWidth`

Maximum width.

`MaxHeight`

Maximum height.

`MinWidth`

Minimum width.

`MinHeight`

Minimum height.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |