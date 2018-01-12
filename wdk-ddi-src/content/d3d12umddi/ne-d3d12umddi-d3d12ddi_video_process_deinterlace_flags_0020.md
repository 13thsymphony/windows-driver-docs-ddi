---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020
title: D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020
author: windows-driver-content
description: Defines the deinterlacing video processor capabilities.
old-location: display\d3d12ddi_video_process_deinterlace_flags.htm
old-project: display
ms.assetid: 7E34CCE5-A771-4EBE-A09B-79424405BFF3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020, D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020
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
req.alt-api: D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020
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
req.typenames: D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020
---

# D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020 enumeration



## -description
Defines the deinterlacing video processor capabilities.



## -syntax

````
typedef enum D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020 { 
  D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_NONE    = 0x0,
  D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_BOB     = 0x1,
  D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_CUSTOM  = 0x80000000
} D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020;
````


## -enum-fields

### -field D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_NONE

No deinterlacing.


### -field D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_BOB

The video processor can perform bob deinterlacing. In bob deinterlacing, missing field lines are interpolated from the lines above and below. Bob deinterlacing does not require reference frames.


### -field D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_CUSTOM

The video processor can perform a custom high quality deinterlacing. This feature requires the number of reference frames indicated in <b>D3D12DDI_VIDEO_PROCESS_FRAME_REFERENCE_SUPPORT</b>. If the video processor does not have the necessary number of reference frames, it falls back to bob deinterlacing.


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