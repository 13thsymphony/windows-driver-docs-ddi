---
UID: NE.dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
title: DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
author: windows-driver-content
description: Identifies a blend operation to be performed on an overlay plane.
old-location: display\dxgi_ddi_multiplane_overlay_blend.htm
old-project: display
ms.assetid: 00b263e7-8655-4219-8e06-e0feba659d04
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: DXGI_DDI_MULTIPLANE_OVERLAY_BLEND, DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
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
req.alt-api: DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
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

# DXGI_DDI_MULTIPLANE_OVERLAY_BLEND enumeration



## -description
Identifies a blend operation to be performed on an overlay plane.


## -syntax

````
typedef enum DXGI_DDI_MULTIPLANE_OVERLAY_BLEND { 
  DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE      = 0x0,
  DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND  = 0x1
} DXGI_DDI_MULTIPLANE_OVERLAY_BLEND;
````


## -enum-fields

### -field DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE

The overlay plane should ignore data in the alpha channel and make the blended plane entirely opaque.

### -field DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND

The overlay plane should use the pre-multiplied alpha channel in this plane to blend it with the plane beneath.

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