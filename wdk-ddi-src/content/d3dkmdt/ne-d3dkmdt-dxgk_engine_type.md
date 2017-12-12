---
UID: NE.d3dkmdt.DXGK_ENGINE_TYPE
title: DXGK_ENGINE_TYPE
author: windows-driver-content
description: Indicates the type of engine on a GPU node. Note the selection rules discussed in Remarks.
old-location: display\dxgk_engine_type.htm
old-project: display
ms.assetid: D94EF91A-784D-4AA2-A43D-6A4AE88CF0A3
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: DXGK_ENGINE_TYPE, DXGK_ENGINE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_ENGINE_TYPE
req.alt-loc: D3dkmdt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# DXGK_ENGINE_TYPE enumeration



## -description
Indicates the type of engine on a GPU node. Note the selection rules discussed in Remarks.



## -syntax

````
typedef enum _DXGK_ENGINE_TYPE { 
  DXGK_ENGINE_TYPE_OTHER             = 0,
  DXGK_ENGINE_TYPE_3D                = 1,
  DXGK_ENGINE_TYPE_VIDEO_DECODE      = 2,
  DXGK_ENGINE_TYPE_VIDEO_ENCODE      = 3,
  DXGK_ENGINE_TYPE_VIDEO_PROCESSING  = 4,
  DXGK_ENGINE_TYPE_SCENE_ASSEMBLY    = 5,
  DXGK_ENGINE_TYPE_COPY              = 6,
  DXGK_ENGINE_TYPE_OVERLAY           = 7
} DXGK_ENGINE_TYPE;
````


## -enum-fields

### -field DXGK_ENGINE_TYPE_OTHER

The engine does not match any of the other <a href="..\d3dkmdt\ne-d3dkmdt-dxgk_engine_type.md">DXGK_ENGINE_TYPE</a> enumeration values. This value is used for proprietary or unique functionality that is not exposed by typical adapters, as well as for an engine that performs work that doesn't fall under another category.


### -field DXGK_ENGINE_TYPE_3D

The adapter's 3-D processing engine. All adapters that are not a <a href="display.kernel_mode_display-only_driver__kmdod__interface">display-only device</a> have one 3-D engine.


### -field DXGK_ENGINE_TYPE_VIDEO_DECODE

The engine that handles video decoding, including decompression of video frames from an input stream into typical YUV surfaces.

The workload packets for an H.264 video codec workload test must appear on either the decode engine or the 3-D engine.


### -field DXGK_ENGINE_TYPE_VIDEO_ENCODE

The engine that handles video encoding, including compression of typical video frames into an encoded video format.


### -field DXGK_ENGINE_TYPE_VIDEO_PROCESSING

The engine that is responsible for any video processing that is done after a video input stream is decoded. Such processing can include RGB surface conversion, filtering, stretching, color correction, deinterlacing, or other steps that are required before the final image is rendered to the display screen.

The workload packets for workload tests must appear on either the video processing engine or the 3-D engine.


### -field DXGK_ENGINE_TYPE_SCENE_ASSEMBLY

The engine that performs vertex processing of 3-D workloads as a preliminary pass prior to the remainder of the 3-D rendering. This engine also stores vertices in bins that tile-based rendering engines use.


### -field DXGK_ENGINE_TYPE_COPY

The engine that is a copy engine used for moving data. This engine can perform subresource updates, blitting, paging, or other similar data handling.

The workload packets for calls to <b>CopySubresourceRegion</b> or <b>UpdateSubResource</b> methods of Direct3D 10 and Direct3D 11 must appear on either the copy engine or the 3-D engine.


### -field DXGK_ENGINE_TYPE_OVERLAY

The virtual engine that is used for synchronized flipping of overlays in Direct3D 9.


## -remarks
The display miniport driver should follow these rules to determine the engine type:

For more information on how to use this enumeration, see <a href="https://msdn.microsoft.com/822FEB3E-A39D-4B33-BD9D-F3166EF99AF8">Enumerating GPU engine capabilities</a>.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>