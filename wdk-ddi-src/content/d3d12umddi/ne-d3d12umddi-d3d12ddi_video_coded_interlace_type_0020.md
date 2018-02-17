---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020
title: D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020
author: windows-driver-content
description: Indicates whether the compressed stream contains only frames (PROGRESSIVE_ONLY) or may contain a mix of progressive and interlaced frames (FIELDS).
old-location: display\d3d12ddi_video_coded_interlace_type.htm
old-project: display
ms.assetid: 5440595D-C692-4349-9332-393CCB11DBFF
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_NONE, d3d12umddi/D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020, d3d12umddi/D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_NONE, D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_FIELD_BASED, D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020, D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020 enumeration [Display Devices], d3d12umddi/D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_FIELD_BASED, display.d3d12ddi_video_coded_interlace_type
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
-	D3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020
---

# D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020 Enumeration
Indicates whether the compressed stream contains only frames (PROGRESSIVE_ONLY) or may contain a mix of progressive and interlaced frames (FIELDS).

## Syntax
````
typedef enum D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020 { 
  D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_NONE         = 0,
  D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_FIELD_BASED  = 1
} D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020;
````

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_FIELD_BASED</td>
                    <td>The coded video stream may contain a mix of progressive and interlaced frames.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_NONE</td>
                    <td>The coded video stream contains only progressive frames.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |