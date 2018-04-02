---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022
title: D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022
author: windows-driver-content
description: Contains values for automatic processing for a driver.
old-location: display\d3d12ddi_video_process_auto_processing_flags.htm
old-project: display
ms.assetid: 37F982EE-8FCB-452F-B589-B14D0E593F1E
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022, D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022 enumeration [Display Devices], D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_ANAMORPHIC_SCALING, D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_COLOR_CORRECTION, D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_CUSTOM, D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_DENOISE, D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_DERINGING, D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_EDGE_ENHANCEMENT, D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_FLESH_TONE_MAPPING, D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_IMAGE_STABILIZATION, D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_NONE, D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_SUPER_RESOLUTION, d3d12umddi/D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022, d3d12umddi/D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_ANAMORPHIC_SCALING, d3d12umddi/D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_COLOR_CORRECTION, d3d12umddi/D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_CUSTOM, d3d12umddi/D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_DENOISE, d3d12umddi/D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_DERINGING, d3d12umddi/D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_EDGE_ENHANCEMENT, d3d12umddi/D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_FLESH_TONE_MAPPING, d3d12umddi/D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_IMAGE_STABILIZATION, d3d12umddi/D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_NONE, d3d12umddi/D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_SUPER_RESOLUTION, display.d3d12ddi_video_process_auto_processing_flags
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022
---

# D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022 Enumeration
Contains values for automatic processing for a driver.

## Syntax
```
typedef enum D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022 {
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_NONE                 ,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_DENOISE              ,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_DERINGING            ,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_EDGE_ENHANCEMENT     ,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_COLOR_CORRECTION     ,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_FLESH_TONE_MAPPING   ,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_IMAGE_STABILIZATION  ,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_SUPER_RESOLUTION     ,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_ANAMORPHIC_SCALING   ,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_CUSTOM
} ;
```

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_NONE</td>
                    <td>No flags. The driver does not support any of the video processing capabilities.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_DENOISE</td>
                    <td>Denoise support.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_DERINGING</td>
                    <td>Deringing support.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_EDGE_ENHANCEMENT</td>
                    <td>Edge enhancement support.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_COLOR_CORRECTION</td>
                    <td>Color correction support.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_FLESH_TONE_MAPPING</td>
                    <td>Flesh tone mapping support.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_IMAGE_STABILIZATION</td>
                    <td>Image stabilization support.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_SUPER_RESOLUTION</td>
                    <td>Enhanced image resolution support.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_ANAMORPHIC_SCALING</td>
                    <td>Anamorphic scaling support.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_CUSTOM</td>
                    <td>Additional processing not represented by these constants.</td>
                </tr>
</table>

## Remarks

These flags are only hints at the type of processing driver performs when automatic processing is enabled.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |