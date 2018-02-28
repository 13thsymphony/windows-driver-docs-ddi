---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
title: "_DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2"
author: windows-driver-content
description: Used by new drivers to report per-plane flip completion after a VSYNC.
old-location: display\dxgk_multiplane_overlay_vsync_info2.htm
old-project: display
ms.assetid: CC1371C5-1BAB-458C-BC7F-9844B2BBEA3A
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2, DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2, display.dxgk_multiplane_overlay_vsync_info2
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
-	DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
product: Windows
targetos: Windows
req.typenames: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
---

# _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure
Used by new drivers to report per-plane flip completion after a VSYNC.

## Syntax
````
typedef struct _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 {
  DWORD                         LayerIndex;
  ULONGLONG                     PresentId;
  DXGKCB_NOTIFY_MPO_VSYNC_FLAGS Flags;
} DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2;
````

## Members


`Flags`

Flag to indicate whether the scheduler should call DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT for this plane

`LayerIndex`

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.

`PresentId`

The 64 bit PresentId specified in the SetVidPnSourceAddressWithMultiPlaneOverlay3() DDI call.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |