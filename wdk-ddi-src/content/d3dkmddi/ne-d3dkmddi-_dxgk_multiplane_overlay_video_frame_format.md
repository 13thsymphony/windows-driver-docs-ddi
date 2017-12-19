---
UID: NE.d3dkmddi._DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
title: _DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
author: windows-driver-content
description: Identifies the overlay plane's video frame format. Only the DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE value is supported.
old-location: display\dxgk_multiplane_overlay_video_frame_format.htm
old-project: display
ms.assetid: 072543cd-d11c-4418-884f-a7823c033a17
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT, DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
req.alt-loc: D3dkmddi.h
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

# _DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT enumeration



## -description
Identifies the overlay plane's video frame format. Only the <b>DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE</b> value is supported.



## -syntax

````
typedef enum _DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT { 
  DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE                    = 0,
  DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST     = 1,
  DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST  = 2
} DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT;
````


## -enum-fields

### -field DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE

Progressive scan format.


### -field DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST

Reserved for system use. Do not use in your driver.


### -field DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST

Reserved for system use. Do not use in your driver.


## -remarks


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
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>