---
UID: NS:d3dkmddi._DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
title: "_DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE"
author: windows-driver-content
description: Specifies the support attributes that the hardware provides for multiplane overlays.
old-location: display\dxgk_check_multiplane_overlay_support_plane.htm
old-project: display
ms.assetid: 28CC4BE1-D4C1-4D22-885B-D50BE5AD6EE6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE, DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE structure [Display Devices], _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE, d3dkmddi/DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE, display.dxgk_check_multiplane_overlay_support_plane
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
product: Windows
targetos: Windows
req.typenames: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
---

# _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE structure
Specifies the support attributes that the hardware provides for multiplane overlays.

## Syntax
````
typedef struct _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE {
  HANDLE                             hAllocation;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID     VidPnSourceId;
  DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES PlaneAttributes;
} DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE;
````

## Members


`hAllocation`

[out] A handle to the allocation. The display miniport driver must set this member to a value that it can use to refer to its private tracking structure for the allocation.

`VidPnSourceId`

[in] The zero-based video present network (VidPN) source identification number of the input for which the support levels are queried.

`PlaneAttributes`

A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_attributes.md">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a> structure that specifies overlay plane attributes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_attributes.md">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a>