---
UID: NE:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
title: DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
author: windows-driver-content
description: Identifies the overlay plane's video frame format. Only the DXGI_DDI_MULIIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE value is supported.
old-location: display\dxgi_ddi_multiplane_overlay_video_frame_format.htm
old-project: display
ms.assetid: b183ae45-bc37-47e5-88b7-ab9a7c148fea
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGI_DDI_MULIIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE, DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST, display.dxgi_ddi_multiplane_overlay_video_frame_format, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST, dxgiddi/DXGI_DDI_MULIIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE, DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST, DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST, DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT enumeration [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Dxgiddi.h
apiname:
-	DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
---

# DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT Enumeration
Identifies the overlay plane's video frame format. Only the <b>DXGI_DDI_MULIIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE</b> value is supported.

## Syntax
````
typedef enum DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT { 
  DXGI_DDI_MULIIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE                    = 0,
  DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST     = 1,
  DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST  = 2
} DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT;
````

## Constants

<table>
            
                <tr>
                    <td>DXGI_DDI_MULIIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE</td>
                    <td>Progressive scan format.</td>
                </tr>
            
                <tr>
                    <td>DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST</td>
                    <td>Reserved for system use. Do not use in your driver.</td>
                </tr>
            
                <tr>
                    <td>DXGI_DDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST</td>
                    <td>Reserved for system use. Do not use in your driver.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | dxgiddi.h (include D3d10umddi.h) |