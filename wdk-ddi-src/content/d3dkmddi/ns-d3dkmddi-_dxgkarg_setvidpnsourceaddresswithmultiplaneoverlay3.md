---
UID: NS:d3dkmddi._DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
title: "_DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3"
author: windows-driver-content
description: Contains arguments for the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay3 function.
old-location: display\dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay3.htm
old-project: display
ms.assetid: 1C6324DB-18E2-4CBC-9589-73DF3EB79503
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay3, d3dkmddi/DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, *IN_OUT_PDXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 structure [Display Devices]
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
-	DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
product: Windows
targetos: Windows
req.typenames: DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
---

# _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 structure
Contains arguments for the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay3 function.

## Syntax
````
typedef struct _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID           VidPnSourceId;
  DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS   InputFlags;
  DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS  OutputFlags;
  UINT                                     PlaneCount;
  DXGK_MULTIPLANE_OVERLAY_PLANE3           **ppPlanes;
  DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION *pPostComposition;
  UINT                                     Duration;
  DXGK_HDR_METADATA                        *pHDRMetaData;
} DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3;
````

## Members


`Duration`

The length of time, in units of 100 nanoseconds, between when the current present operation flips to the screen and the next vertical blanking interrupt occurs.

If zero, the refresh rate should be the default rate based on the current mode.

`InputFlags`

A DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS structure that identifies the type of display operation to perform.

`OutputFlags`

A DXGK_SETVIPNSOURCEADDRESS_OUTPUT_FLAGS structure that returns information from the driver.

`pHDRMetaData`

Pointer to a DXGK_HDR_METADATA structure indicating any metadata information that might be available. A NULL value indicates that no new metadata is available.

`PlaneCount`

The number of overlay planes in the ppPlanes list.

`pPostComposition`

Pointer to a DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION structure containing virtual mode information and other transform information that should be applied after the planes have been composed.

If NULL, no post composition transforms should be applied.

`ppPlanes`

An array of pointers to a DXGK_MULTIPLANE_OVERLAY_PLANE3 structures that specify the overlay planes to display.

`VidPnSourceId`

An integer that identifies a video present source on the display adapter.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |