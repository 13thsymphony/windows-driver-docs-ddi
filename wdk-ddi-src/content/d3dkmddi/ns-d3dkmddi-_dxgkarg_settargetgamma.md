---
UID: NS:d3dkmddi._DXGKARG_SETTARGETGAMMA
title: "_DXGKARG_SETTARGETGAMMA"
author: windows-driver-content
description: Used to hold the arguments for DXGKDDI_SETTARGETGAMMA.
old-location: display\dxgkarg_settargetgamma.htm
old-project: display
ms.assetid: 94BA40BD-3B56-44EF-BAD4-49556E68C550
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_DXGKARG_SETTARGETGAMMA, DXGKARG_SETTARGETGAMMA, d3dkmddi/PDXGKARG_SETTARGETGAMMA, PDXGKARG_SETTARGETGAMMA structure pointer [Display Devices], display.dxgkarg_settargetgamma, d3dkmddi/DXGKARG_SETTARGETGAMMA, DXGKARG_SETTARGETGAMMA structure [Display Devices], PDXGKARG_SETTARGETGAMMA"
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
-	DXGKARG_SETTARGETGAMMA
product: Windows
targetos: Windows
req.typenames: DXGKARG_SETTARGETGAMMA
---

# _DXGKARG_SETTARGETGAMMA structure
Used to hold the arguments for <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_settargetgamma.md">DXGKDDI_SETTARGETGAMMA</a>.

## Syntax
````
typedef struct _DXGKARG_SETTARGETGAMMA {
  D3DDDI_VIDEO_PRESENT_TARGET_ID TargetId;
  D3DKMDT_GAMMA_RAMP             GammaRamp;
} DXGKARG_SETTARGETGAMMA, *PDXGKARG_SETTARGETGAMMA;
````

## Members


`GammaRamp`

A <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_gamma_ramp.md">D3DKMDT_GAMMA_RAMP</a> struct which describes the type of gamma ramp to set and the buffer containing the ramp data.

`TargetId`

The identifier of a display adapter's video present target.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |