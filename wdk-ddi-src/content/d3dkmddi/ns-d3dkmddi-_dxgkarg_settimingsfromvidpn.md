---
UID: NS:d3dkmddi._DXGKARG_SETTIMINGSFROMVIDPN
title: "_DXGKARG_SETTIMINGSFROMVIDPN"
author: windows-driver-content
description: Used to hold the arguments for DXGKDDI_SETTIMINGSFROMVIDPN.
old-location: display\dxgkarg_settimingsfromvidpn.htm
old-project: display
ms.assetid: 14D652C4-9812-481E-8E69-A6D7923F01A3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*IN_OUT_PDXGKARG_SETTIMINGSFROMVIDPN, DXGKARG_SETTIMINGSFROMVIDPN, DXGKARG_SETTIMINGSFROMVIDPN structure [Display Devices], PDXGKARG_SETTIMINGSFROMVIDPN, PDXGKARG_SETTIMINGSFROMVIDPN structure pointer [Display Devices], _DXGKARG_SETTIMINGSFROMVIDPN, d3dkmddi/DXGKARG_SETTIMINGSFROMVIDPN, d3dkmddi/PDXGKARG_SETTIMINGSFROMVIDPN, display.dxgkarg_settimingsfromvidpn"
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
-	DXGKARG_SETTIMINGSFROMVIDPN
product: Windows
targetos: Windows
req.typenames: DXGKARG_SETTIMINGSFROMVIDPN
---

# _DXGKARG_SETTIMINGSFROMVIDPN structure
Used to hold the arguments for <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md">DXGKDDI_SETTIMINGSFROMVIDPN</a>.

## Syntax
````
typedef struct _DXGKARG_SETTIMINGSFROMVIDPN {
  D3DKMDT_HVIDPN            hFunctionalVidPn;
  DXGK_SET_TIMING_FLAGS     SetFlags;
  PDXGK_SET_TIMING_RESULTS  pResultsFlags;
  UINT                      PathCount;
  DXGK_SET_TIMING_PATH_INFO *pSetTimingPathInfo;
} DXGKARG_SETTIMINGSFROMVIDPN, *PDXGKARG_SETTIMINGSFROMVIDPN;
````

## Members


`hFunctionalVidPn`

Handle to a functional VidPn which describes the display configuration the OS is attempting to apply.

`SetFlags`

A DXGK_SET_TIMING_FLAGS structure that requests specific actions from the driver on the SetTimingsFromVidPn call.

`pResultsFlags`

Pointer to a DXGK_SET_TIMING_RESULTS structure that the driver should use to report overall results from the SetTimingsFromVidPn call.

`PathCount`

Number of pointers in the array pointed to by pSetTimingPathInfo.

`pSetTimingPathInfo`

An array of pointers to DXGK_SET_TIMING_PATH_INFO structures that specify per path details of the timings to be set. It also allows feedback from the driver on additional work the OS needs to do either before the timings changes can be made, or after changes are complete.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |