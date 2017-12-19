---
UID: NE.dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
title: DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
author: windows-driver-content
description: Identifies the overlay plane's stereo flip mode. Only the DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE value is supported.
old-location: display\dxgi_ddi_multiplane_overlay_stereo_flip_mode.htm
old-project: display
ms.assetid: f44317c5-661c-42f6-847b-b325e4c1321a
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE, DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
req.alt-loc: Dxgiddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE enumeration



## -description
Identifies the overlay plane's stereo flip mode. Only the <b>DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE</b> value is supported.



## -syntax

````
typedef enum DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE { 
  DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE    = 0,
  DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0  = 1,
  DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1  = 2
} DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE;
````


## -enum-fields

### -field DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE

The overplay plane data is not presented in stereo mode.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0

Reserved for system use. Do not use in your driver.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1

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
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>