---
UID: NE:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
title: DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
author: windows-driver-content
description: Identifies a blend operation to be performed on an overlay plane.
old-location: display\dxgi_ddi_multiplane_overlay_blend.htm
old-project: display
ms.assetid: 00b263e7-8655-4219-8e06-e0feba659d04
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGI_DDI_MULTIPLANE_OVERLAY_BLEND, DXGI_DDI_MULTIPLANE_OVERLAY_BLEND enumeration [Display Devices], DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND, DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE, display.dxgi_ddi_multiplane_overlay_blend, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_BLEND, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dxgiddi.h
api_name:
-	DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_MULTIPLANE_OVERLAY_BLEND
---

# DXGI_DDI_MULTIPLANE_OVERLAY_BLEND Enumeration
Identifies a blend operation to be performed on an overlay plane.

## Syntax
```
typedef enum DXGI_DDI_MULTIPLANE_OVERLAY_BLEND {
  DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE      ,
  DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND
} ;
```

## Constants

<table>
            
                <tr>
                    <td>DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_OPAQUE</td>
                    <td>The overlay plane should ignore data in the alpha channel and make the blended plane entirely opaque.</td>
                </tr>
            
                <tr>
                    <td>DXGI_DDI_MULTIPLANE_OVERLAY_BLEND_ALPHABLEND</td>
                    <td>The overlay plane should use the pre-multiplied alpha channel in this plane to blend it with the plane beneath.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | dxgiddi.h (include D3d10umddi.h) |