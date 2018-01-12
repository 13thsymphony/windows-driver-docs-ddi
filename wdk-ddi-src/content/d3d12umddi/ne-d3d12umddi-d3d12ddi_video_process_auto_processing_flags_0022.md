---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022
title: D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022
author: windows-driver-content
description: Contains values for automatic processing for a driver.
old-location: display\d3d12ddi_video_process_auto_processing_flags.htm
old-project: display
ms.assetid: 37F982EE-8FCB-452F-B589-B14D0E593F1E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022, D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022
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
req.alt-api: D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022
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
req.typenames: D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022
---

# D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022 enumeration



## -description
Contains values for automatic processing for a driver.



## -syntax

````
typedef enum D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022 { 
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_NONE                 = 0x0,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_DENOISE              = 0x01,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_DERINGING            = 0x02,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_EDGE_ENHANCEMENT     = 0x04,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_COLOR_CORRECTION     = 0x08,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_FLESH_TONE_MAPPING   = 0x10,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_IMAGE_STABILIZATION  = 0x20,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_SUPER_RESOLUTION     = 0x40,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_ANAMORPHIC_SCALING   = 0x80,
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_CUSTOM               = 0x100
} D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022;
````


## -enum-fields

### -field D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_NONE

No flags. The driver does not support any of the video processing capabilities. 


### -field D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_DENOISE

Denoise support.


### -field D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_DERINGING

Deringing support.


### -field D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_EDGE_ENHANCEMENT

Edge enhancement support.


### -field D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_COLOR_CORRECTION

Color correction support.


### -field D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_FLESH_TONE_MAPPING

Flesh tone mapping support.


### -field D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_IMAGE_STABILIZATION

Image stabilization support.


### -field D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_SUPER_RESOLUTION

Enhanced image resolution support.


### -field D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_ANAMORPHIC_SCALING

Anamorphic scaling support.


### -field D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAG_0022_CUSTOM

Additional processing not represented by these constants.


## -remarks
These flags are only hints at the type of processing driver performs when automatic processing is enabled.


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