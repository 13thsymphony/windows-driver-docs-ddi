---
UID: NE:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
title: "_DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT"
author: windows-driver-content
description: Identifies the overlay plane's video frame format. Only the DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE value is supported.
old-location: display\dxgk_multiplane_overlay_video_frame_format.htm
old-project: display
ms.assetid: 072543cd-d11c-4418-884f-a7823c033a17
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT, DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT enumeration [Display Devices], DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST, DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST, DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE, _DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE, display.dxgk_multiplane_overlay_video_frame_format
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
product:
- Windows
targetos: Windows
req.typenames: DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
---

# _DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT Enumeration
Identifies the overlay plane's video frame format. Only the <b>DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE</b> value is supported.

## Syntax
```
typedef enum _DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT {
  DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE                    ,
  DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST     ,
  DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST
} DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT;
```

## Constants

<table>
            
                <tr>
                    <td>DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE</td>
                    <td>Progressive scan format.</td>
                </tr>
            
                <tr>
                    <td>DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST</td>
                    <td>Reserved for system use. Do not use in your driver.</td>
                </tr>
            
                <tr>
                    <td>DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST</td>
                    <td>Reserved for system use. Do not use in your driver.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |