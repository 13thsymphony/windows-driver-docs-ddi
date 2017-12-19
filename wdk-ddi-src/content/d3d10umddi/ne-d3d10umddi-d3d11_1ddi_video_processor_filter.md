---
UID: NE.d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_FILTER
title: D3D11_1DDI_VIDEO_PROCESSOR_FILTER
author: windows-driver-content
description: Identifies a video processor filter.
old-location: display\d3d11_1ddi_video_processor_filter.htm
old-project: display
ms.assetid: 189ad1c2-3828-468a-a99d-12d85da6bf63
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_FILTER, D3D11_1DDI_VIDEO_PROCESSOR_FILTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_VIDEO_PROCESSOR_FILTER
req.alt-loc: D3d10umddi.h
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

# D3D11_1DDI_VIDEO_PROCESSOR_FILTER enumeration



## -description
Identifies a video processor filter.



## -syntax

````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_FILTER { 
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_BRIGHTNESS          = 0,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CONTRAST            = 1,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_HUE                 = 2,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_SATURATION          = 3,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_NOISE_REDUCTION     = 4,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_EDGE_ENHANCEMENT    = 5,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_ANAMORPHIC_SCALING  = 6,
  D3D11_1DDI_VIDEO_PROCESSOR_FILTER_STEREO_ADJUSTMENT   = 7
} D3D11_1DDI_VIDEO_PROCESSOR_FILTER;
````


## -enum-fields

### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_BRIGHTNESS

Brightness filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CONTRAST

Contrast filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_HUE

Hue filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_SATURATION

Saturation filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_NOISE_REDUCTION

Noise reduction filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_EDGE_ENHANCEMENT

Edge enhancement filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_ANAMORPHIC_SCALING

Anamorphic scaling filter.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FILTER_STEREO_ADJUSTMENT

Stereo adjustment filter. When stereo 3-D video is enabled, this filter adjusts the offset between the left and right views, allowing the user to reduce potential eye strain.

The filter value indicates the amount by which the left and right views are adjusted. A positive value shifts the images away from each other: the left image toward the left, and the right image toward the right. A negative value shifts the images in the opposite directions, closer to each other.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>