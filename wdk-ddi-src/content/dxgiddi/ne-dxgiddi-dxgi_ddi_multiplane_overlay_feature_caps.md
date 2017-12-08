---
UID: NE.dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS
title: DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS
author: windows-driver-content
description: Identifies overlay capabilities.
old-location: display\dxgi_ddi_multiplane_overlay_feature_caps.htm
old-project: display
ms.assetid: f64b3470-b4ae-4d3a-87ac-249429f17dfe
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS, DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS
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
req.alt-api: DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS
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

# DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS enumeration



## -description
Identifies overlay capabilities.


## -syntax

````
typedef enum DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS { 
  DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_ROTATION         = 0x1,
  DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_VERTICAL_FLIP    = 0x2,
  DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HORIZONTAL_FLIP  = 0x4,
  DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_DEINTERLACE      = 0x8,
  DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_STEREO           = 0x10
} DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS;
````


## -enum-fields

### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_ROTATION

The overlay plane can rotate the data 90, 180, and 270 degrees.

### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_VERTICAL_FLIP

The overlay plane can flip the data vertically, making it appear upside-down.

### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HORIZONTAL_FLIP

The overlay plane can flip the data horizontally, making it appear as a right-to-left mirror image.

### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_DEINTERLACE

Reserved for system use. The user-mode display driver should not use this value.

### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_STEREO

Reserved for system use. The user-mode display driver should not use this value.

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