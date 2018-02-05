---
UID : NE:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
title : "_DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE"
author : windows-driver-content
description : Identifies the overlay plane's stereo flip mode. Only the DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE value is supported.
old-location : display\dxgk_multiplane_overlay_stereo_flip_mode.htm
old-project : display
ms.assetid : f226f276-c5d3-460d-9f52-c66ccfd3393f
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1, display.dxgk_multiplane_overlay_stereo_flip_mode, DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE enumeration [Display Devices], DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE, DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE, DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0, _DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3dkmddi.h
req.include-header : D3dkmddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
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
req.typenames : DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
---

# _DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE Enumeration
Identifies the overlay plane's stereo flip mode. Only the <b>DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE</b> value is supported.

## Syntax
````
typedef enum _DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE { 
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE    = 0,
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0  = 1,
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1  = 2
} DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE;
````

## Constants

<table>

<tr>
<td>DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0</td>
<td>Reserved for system use. Do not use in your driver.</td>
</tr>

<tr>
<td>DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1</td>
<td>Reserved for system use. Do not use in your driver.</td>
</tr>

<tr>
<td>DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE</td>
<td>The overplay plane data is not presented in stereo mode.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |