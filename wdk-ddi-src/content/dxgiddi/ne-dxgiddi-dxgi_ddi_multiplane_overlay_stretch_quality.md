---
UID: NE.dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY
title: DXGI_DDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY
author: windows-driver-content
description: Identifies filtering processes that the hardware should perform when it stretches or shrinks multiplane overlay data.
old-location: display\dxgi_ddi_multiplane_overlay_stretch_quality.htm
old-project: display
ms.assetid: 550C09F4-8684-4B6F-BB62-8514721A9B32
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: DXGI_DDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY, DXGI_DDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY
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
req.alt-api: DXGI_DDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY
req.alt-loc: Dxgiddi.h
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
---

# DXGI_DDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY enumeration



## -description
Identifies filtering processes that the hardware should perform when it stretches or shrinks multiplane overlay data.


## -syntax

````
typedef enum DXGI_DDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY { 
  DXGI_DDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY_BILINEAR  = 0x1,
  DXGI_DDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY_HIGH      = 0x2
} DXGI_DDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY;
````


## -enum-fields

### -field DXGI_DDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY_BILINEAR

When the hardware stretches or shrinks the data, it should perform bilinear filtering. If the hardware lacks enough resources to perform bilinear shrinking, the user-mode display driver can use point sampling.

### -field DXGI_DDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY_HIGH

When the hardware stretches or shrinks the data, it should perform the highest quality filtering that it supports.

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
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>