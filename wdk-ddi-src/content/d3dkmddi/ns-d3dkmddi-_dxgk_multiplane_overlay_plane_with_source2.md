---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2
title: "_DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2"
author: windows-driver-content
description: Used in a call to the DxgkDdiCheckMultiPlaneOverlaySupport3 function to check details on hardware support for multi-plane overlays.
old-location: display\dxgk_multiplane_overlay_plane_with_source2.htm
old-project: display
ms.assetid: A9508EBF-0B33-48D7-AD57-31E38D77F5DA
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2, DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2 structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2, display.dxgk_multiplane_overlay_plane_with_source2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2
product:
- Windows
targetos: Windows
req.typenames: DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2
---

# _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2 structure
Used in a call to the <i>DxgkDdiCheckMultiPlaneOverlaySupport3</i> function to check details on hardware support for multi-plane overlays.

## Syntax
```
typedef struct _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2 {
  HANDLE                              hAllocation;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID      VidPnSourceId;
  UINT                                LayerIndex;
  DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3 PlaneAttributes;
} DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2;
```

## Members


`hAllocation`

A handle to the allocation.

`VidPnSourceId`

The zero-based video present network (VidPN) source identification number of the input for which the support levels are queried.

`LayerIndex`

The zero based index indicating the Z order of the overlay plane.

`PlaneAttributes`

A DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3 structure that specifies overlay plane attributes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |