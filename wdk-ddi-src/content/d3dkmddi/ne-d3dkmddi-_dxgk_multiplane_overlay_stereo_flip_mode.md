---
UID: NE.d3dkmddi._DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
title: _DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
author: windows-driver-content
description: Identifies the overlay plane's stereo flip mode. Only the DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE value is supported.
old-location: display\dxgk_multiplane_overlay_stereo_flip_mode.htm
old-project: display
ms.assetid: f226f276-c5d3-460d-9f52-c66ccfd3393f
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE, DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
req.alt-loc: D3dkmddi.h
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
---

# _DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE enumeration



## -description
Identifies the overlay plane's stereo flip mode. Only the <b>DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE</b> value is supported.




## -syntax

````
typedef enum _DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE { 
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE    = 0,
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0  = 1,
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1  = 2
} DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE;
````


## -enum-fields

### -field DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE

The overplay plane data is not presented in stereo mode.


### -field DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0

Reserved for system use. Do not use in your driver.


### -field DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1

Reserved for system use. Do not use in your driver.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>