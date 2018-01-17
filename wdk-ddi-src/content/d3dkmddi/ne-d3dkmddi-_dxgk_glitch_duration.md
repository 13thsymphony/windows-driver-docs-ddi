---
UID: NE:d3dkmddi._DXGK_GLITCH_DURATION
title: _DXGK_GLITCH_DURATION
author: windows-driver-content
description: Enumeration that describes the duration of a user visible effect of a glitch during a SetTimingsFromVidPn call.
old-location: display\dxgk_glitch_duration.htm
old-project: display
ms.assetid: 8B6597A7-D652-4143-9320-7FB8E98FE8EC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_GLITCH_DURATION, DXGK_GLITCH_DURATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_GLITCH_DURATION
req.alt-loc: d3dkmddi.h
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
req.typenames: DXGK_GLITCH_DURATION
---

# _DXGK_GLITCH_DURATION enumeration



## -description
Enumeration that describes the duration of a user visible effect of a glitch during a SetTimingsFromVidPn call.



## -syntax

````
typedef enum _DXGK_GLITCH_DURATION { 
  DXGK_GLITCH_DURATION_INDEFINITE    = 0,
  DXGK_GLITCH_DURATION_MULTI_FRAME   = 1,
  DXGK_GLITCH_DURATION_SINGLE_FRAME  = 2,
  DXGK_GLITCH_DURATION_MULTI_LINE    = 3,
  DXGK_GLITCH_DURATION_SINGLE_LINE   = 4,
  DXGK_GLITCH_DURATION_NONE          = 255
} DXGK_GLITCH_DURATION;
````


## -enum-fields

### -field DXGK_GLITCH_DURATION_INDEFINITE

Indicates that a glitch is unresolved.


### -field DXGK_GLITCH_DURATION_MULTI_FRAME

Indicates that a glitch lasted for multiple frames.


### -field DXGK_GLITCH_DURATION_SINGLE_FRAME

Indicates that a glitch lasted for no more than one frame.


### -field DXGK_GLITCH_DURATION_MULTI_LINE

Indicates that a glitch lasted for multiple lines within a frame.


### -field DXGK_GLITCH_DURATION_SINGLE_LINE

Indicates that a glitch lasted for no more than one line.


### -field DXGK_GLITCH_DURATION_NONE

Indicates that there was no user visible glitch.


## -remarks
