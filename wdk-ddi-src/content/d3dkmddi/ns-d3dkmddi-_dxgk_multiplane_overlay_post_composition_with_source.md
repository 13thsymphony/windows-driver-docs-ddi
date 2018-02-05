---
UID : NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE
title : "_DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE"
author : windows-driver-content
description : Used in a call to the DxgkDdiCheckMultiPlaneOverlaySupport3 function to check details on hardware support for post composition transform support.
old-location : display\dxgk_multiplane_overlay_post_composition_with_source.htm
old-project : display
ms.assetid : F997E3DB-630D-41C8-B659-36376E05A6B7
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE structure [Display Devices], display.dxgk_multiplane_overlay_post_composition_with_source, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE, _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE, DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE
---

# _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE structure
Used in a call to the <b>DxgkDdiCheckMultiPlaneOverlaySupport3 </b>function to check details on hardware support for post composition transform support.

## Syntax
````
typedef struct _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID            VidPnSourceId;
  DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION  PostComposition;
} DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE;
````

## Members


`PostComposition`

A DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION structure that specifies additional transforms that should be applied after the planes are composed.

`VidPnSourceId`

The zero-based video present network (VidPN) source identification number of the input for which the support levels are queried.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |