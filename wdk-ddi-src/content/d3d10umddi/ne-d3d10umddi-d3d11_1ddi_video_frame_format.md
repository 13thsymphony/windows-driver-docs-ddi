---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_FRAME_FORMAT
title: D3D11_1DDI_VIDEO_FRAME_FORMAT
author: windows-driver-content
description: Describes how a video stream is interlaced.
old-location: display\d3d11_1ddi_video_frame_format.htm
old-project: display
ms.assetid: 36af5af2-dfb1-4827-8898-93e52f4c8312
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3D11_1DDI_VIDEO_FRAME_FORMAT, d3d10umddi/D3D11_1DDI_VIDEO_FRAME_FORMAT, D3D11_1DDI_VIDEO_FRAME_FORMAT enumeration [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST, D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST, display.d3d11_1ddi_video_frame_format, d3d10umddi/D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST, D3D11_1DDI_VIDEO_FRAME_FORMAT_PROGRESSIVE, d3d10umddi/D3D11_1DDI_VIDEO_FRAME_FORMAT_PROGRESSIVE, D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST
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
-	D3d10umddi.h
apiname:
-	D3D11_1DDI_VIDEO_FRAME_FORMAT
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_FRAME_FORMAT
---

# D3D11_1DDI_VIDEO_FRAME_FORMAT Enumeration
Describes how a video stream is interlaced.

## Syntax
````
typedef enum D3D11_1DDI_VIDEO_FRAME_FORMAT { 
  D3D11_1DDI_VIDEO_FRAME_FORMAT_PROGRESSIVE                    = 0,
  D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST     = 1,
  D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST  = 2
} D3D11_1DDI_VIDEO_FRAME_FORMAT;
````

## Constants

<table>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST</td>
                    <td>Frame are interlaced. The bottom field of each frame is displayed first.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST</td>
                    <td>Frames are interlaced. The top field of each frame is displayed first.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_FRAME_FORMAT_PROGRESSIVE</td>
                    <td>Frames are progressive.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |