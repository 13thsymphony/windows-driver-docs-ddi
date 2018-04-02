---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_FIELD_TYPE_0020
title: D3D12DDI_VIDEO_FIELD_TYPE_0020
author: windows-driver-content
description: Contains values that define how a video frame is interlaced.
old-location: display\d3d12ddi_video_field_type.htm
old-project: display
ms.assetid: 869BF62F-C8FE-4AD8-A413-65FBE97EE7FB
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_VIDEO_FIELD_TYPE_0020, D3D12DDI_VIDEO_FIELD_TYPE_0020 enumeration [Display Devices], D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_BOTTOM_FIELD_FIRST, D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_TOP_FIELD_FIRST, D3D12DDI_VIDEO_FIELD_TYPE_0020_NONE, d3d12umddi/D3D12DDI_VIDEO_FIELD_TYPE_0020, d3d12umddi/D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_BOTTOM_FIELD_FIRST, d3d12umddi/D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_TOP_FIELD_FIRST, d3d12umddi/D3D12DDI_VIDEO_FIELD_TYPE_0020_NONE, display.d3d12ddi_video_field_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3D12DDI_VIDEO_FIELD_TYPE_0020
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_FIELD_TYPE_0020
---

# D3D12DDI_VIDEO_FIELD_TYPE_0020 Enumeration
Contains values that define how a video frame is interlaced.

## Syntax
```
typedef enum D3D12DDI_VIDEO_FIELD_TYPE_0020 {
  D3D12DDI_VIDEO_FIELD_TYPE_0020_NONE                           ,
  D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_TOP_FIELD_FIRST     ,
  D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_BOTTOM_FIELD_FIRST
} ;
```

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_VIDEO_FIELD_TYPE_0020_NONE</td>
                    <td>Frame is progressive.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_TOP_FIELD_FIRST</td>
                    <td>Frame is interlaced. The top field of each frame is displayed first.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_BOTTOM_FIELD_FIRST</td>
                    <td>Frame is interlaced. The bottom field of each frame is displayed first.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |