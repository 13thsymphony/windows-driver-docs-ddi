---
UID: NE.d3d12umddi.D3D12DDI_VIDEO_PROCESS_FILTER_0020
title: D3D12DDI_VIDEO_PROCESS_FILTER_0020
author: windows-driver-content
description: Contains video process filters.
old-location: display\d3d12ddi_video_process_filter_0020.htm
old-project: display
ms.assetid: A69E2A06-EA08-465C-A1E9-2D7FAB4E2F81
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_FILTER_0020, D3D12DDI_VIDEO_PROCESS_FILTER_0020
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
req.alt-api: D3D12DDI_VIDEO_PROCESS_FILTER_0020
req.alt-loc: D3d12umddi.h
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
---

# D3D12DDI_VIDEO_PROCESS_FILTER_0020 enumeration



## -description
Contains video process filters.



## -syntax

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


## -enum-fields

### -field D3D12DDI_VIDEO_PROCESS_FILTER_0020_BRIGHTNESS

The video processor can adjust the brightness level. 


### -field D3D12DDI_VIDEO_PROCESS_FILTER_0020_CONTRAST

The video processor can adjust the contrast level. 


### -field D3D12DDI_VIDEO_PROCESS_FILTER_0020_HUE

The video processor can adjust hue. 


### -field D3D12DDI_VIDEO_PROCESS_FILTER_0020_SATURATION

The video processor can adjust the saturation level.


### -field D3D12DDI_VIDEO_PROCESS_FILTER_0020_NOISE_REDUCTION

The video processor can perform noise reduction. 


### -field D3D12DDI_VIDEO_PROCESS_FILTER_0020_EDGE_ENHANCEMENT

The video processor can perform edge enhancement. 


### -field D3D12DDI_VIDEO_PROCESS_FILTER_0020_ANAMORPHIC_SCALING

The video processor can perform anamorphic scaling. Anamorphic scaling can be used to stretch 4:3 content to a widescreen 16:9 aspect ratio. 


### -field D3D12DDI_VIDEO_PROCESS_FILTER_0020_STEREO_ADJUSTMENT

For stereo 3D video, the video processor can adjust the offset between the left and right views, allowing the user to reduce potential eye strain.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>