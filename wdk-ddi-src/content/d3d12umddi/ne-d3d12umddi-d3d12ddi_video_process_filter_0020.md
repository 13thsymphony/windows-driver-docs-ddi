---
UID : NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_FILTER_0020
title : D3D12DDI_VIDEO_PROCESS_FILTER_0020
author : windows-driver-content
description : Contains video process filters.
old-location : display\d3d12ddi_video_process_filter_0020.htm
old-project : display
ms.assetid : A69E2A06-EA08-465C-A1E9-2D7FAB4E2F81
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_VIDEO_PROCESS_FILTER_0020 enumeration [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_NOISE_REDUCTION, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_HUE, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_SATURATION, D3D12DDI_VIDEO_PROCESS_FILTER_0020_SATURATION, D3D12DDI_VIDEO_PROCESS_FILTER_0020_EDGE_ENHANCEMENT, D3D12DDI_VIDEO_PROCESS_FILTER_0020_ANAMORPHIC_SCALING, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_EDGE_ENHANCEMENT, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020, display.d3d12ddi_video_process_filter_0020, D3D12DDI_VIDEO_PROCESS_FILTER_0020_BRIGHTNESS, D3D12DDI_VIDEO_PROCESS_FILTER_0020_HUE, D3D12DDI_VIDEO_PROCESS_FILTER_0020_NOISE_REDUCTION, D3D12DDI_VIDEO_PROCESS_FILTER_0020, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_ANAMORPHIC_SCALING, D3D12DDI_VIDEO_PROCESS_FILTER_0020_STEREO_ADJUSTMENT, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_BRIGHTNESS, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_CONTRAST, D3D12DDI_VIDEO_PROCESS_FILTER_0020_CONTRAST, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_STEREO_ADJUSTMENT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3d12umddi.h
req.include-header : D3d12umddi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
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
req.typenames : D3D12DDI_VIDEO_PROCESS_FILTER_0020
---

# D3D12DDI_VIDEO_PROCESS_FILTER_0020 Enumeration
Contains video process filters.

## Syntax
````
typedef enum _D3D12DDI_VIDEO_PROCESS_FILTER_0020 { 
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_BRIGHTNESS          = 0,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_CONTRAST            = 1,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_HUE                 = 2,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_SATURATION          = 3,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_NOISE_REDUCTION     = 4,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_EDGE_ENHANCEMENT    = 5,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_ANAMORPHIC_SCALING  = 6,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_STEREO_ADJUSTMENT   = 7
} D3D12DDI_VIDEO_PROCESS_FILTER_0020;
````

## Constants

<table>

<tr>
<td>D3D12DDI_VIDEO_PROCESS_FILTER_0020_ANAMORPHIC_SCALING</td>
<td>The video processor can perform anamorphic scaling. Anamorphic scaling can be used to stretch 4:3 content to a widescreen 16:9 aspect ratio.</td>
</tr>

<tr>
<td>D3D12DDI_VIDEO_PROCESS_FILTER_0020_BRIGHTNESS</td>
<td>The video processor can adjust the brightness level.</td>
</tr>

<tr>
<td>D3D12DDI_VIDEO_PROCESS_FILTER_0020_CONTRAST</td>
<td>The video processor can adjust the contrast level.</td>
</tr>

<tr>
<td>D3D12DDI_VIDEO_PROCESS_FILTER_0020_EDGE_ENHANCEMENT</td>
<td>The video processor can perform edge enhancement.</td>
</tr>

<tr>
<td>D3D12DDI_VIDEO_PROCESS_FILTER_0020_HUE</td>
<td>The video processor can adjust hue.</td>
</tr>

<tr>
<td>D3D12DDI_VIDEO_PROCESS_FILTER_0020_NOISE_REDUCTION</td>
<td>The video processor can perform noise reduction.</td>
</tr>

<tr>
<td>D3D12DDI_VIDEO_PROCESS_FILTER_0020_SATURATION</td>
<td>The video processor can adjust the saturation level.</td>
</tr>

<tr>
<td>D3D12DDI_VIDEO_PROCESS_FILTER_0020_STEREO_ADJUSTMENT</td>
<td>For stereo 3D video, the video processor can adjust the offset between the left and right views, allowing the user to reduce potential eye strain.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |