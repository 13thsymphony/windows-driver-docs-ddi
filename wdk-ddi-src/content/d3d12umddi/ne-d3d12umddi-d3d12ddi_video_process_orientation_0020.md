---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020
title: D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020
author: windows-driver-content
description: The orientation to be performed by the video processor.
old-location: display\d3d12ddi_video_process_orientation.htm
old-project: display
ms.assetid: 0901AA41-DDA6-46F2-99CA-E45718346A86
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020, D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020
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
req.alt-api: D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020
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
req.typenames: D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020
---

# D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020 enumeration



## -description
The orientation to be performed by the video processor.



## -syntax

````
typedef enum D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020 { 
  D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_DEFAULT                        = 0,
  D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_FLIP_HORIZONTAL                = 1,
  D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_CLOCKWISE_90                   = 2,
  D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_CLOCKWISE_90_FLIP_HORIZONTAL   = 3,
  D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_CLOCKWISE_180                  = 4,
  D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_FLIP_VERTICAL                  = 5,
  D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_CLOCKWISE_180_FLIP_HORIZONTAL  = 5,
  D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_CLOCKWISE_270                  = 6,
  D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_CLOCKWISE_270_FLIP_HORIZONTAL  = 7
} D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020;
````


## -enum-fields

### -field D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_DEFAULT

No change to the orientation.


### -field D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_FLIP_HORIZONTAL

Flip the image horizontally.


### -field D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_CLOCKWISE_90

Rotate the image clockwise 90 degrees.


### -field D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_CLOCKWISE_90_FLIP_HORIZONTAL

Rotate the image clockwise 90 degrees and then flips it horizontally.


### -field D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_CLOCKWISE_180

Rotate the image clockwise 180 degrees.


### -field D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_FLIP_VERTICAL

Flip the image vertically. This is the same as the <b>D3D12DDI_VIDEO_PROCESS_ORIENTATION_CLOCKWISE_180_FLIP_HORIZONTAL</b> constant.


### -field D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_CLOCKWISE_180_FLIP_HORIZONTAL

Rotate the image clockwise 180 degrees and then flip horizontally. This is the same as the <b>D3D12DDI_VIDEO_PROCESS_ORIENTATION_FLIP_VERTICAL</b> constant.


### -field D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_CLOCKWISE_270

Rotate the image clockwise 270 degrees.


### -field D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020_CLOCKWISE_270_FLIP_HORIZONTAL

Rotate the image clockwise 270 degrees and then flips horizontally.


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