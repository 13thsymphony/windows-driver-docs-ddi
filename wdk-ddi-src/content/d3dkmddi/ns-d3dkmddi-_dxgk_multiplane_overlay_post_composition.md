---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION
title: "_DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION"
author: windows-driver-content
description: Specifies information about any additional transforms that should occur after the planes are composed.
old-location: display\dxgk_multiplane_overlay_post_composition.htm
old-project: display
ms.assetid: 71D57E42-C1E7-4A0E-80B3-DD39388552C5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION, display.dxgk_multiplane_overlay_post_composition, _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION, DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION structure [Display Devices], DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION
product: Windows
targetos: Windows
req.typenames: DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION
---

# _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION structure
Specifies information about any additional transforms that should occur after the planes are composed.

## Syntax
````
typedef struct _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION {
  DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_FLAGS        Flags;
  RECT                                                  SrcRect;
  RECT                                                  DstRect;
  D3DDDI_ROTATION                                       Rotation;
} DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION;
````

## Members


`DstRect`

Contains the destination rect of the virtual mode.

`Flags`

A DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_FLAGS structure indicating additional transform information.

`Rotation`

Indicates additional rotation that should occur on the final image.

`SrcRect`

Contains the source rect of the virtual mode.

## Remarks
The source mode contains the virtual mode size and the destination rectangle indicates how the virtual mode maps to the physical mode.

For example, if a 1024x768 virtual mode is used with 1920x1080 physical mode, the following configurations are possible:

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |