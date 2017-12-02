---
UID: NE.d3dumddi.D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
title: D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
author: windows-driver-content
description: Identifies the overlay plane's video frame format. Only the D3DDDI_MULIIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE value is supported.
old-location: display\d3dddi_multiplane_overlay_video_frame_format.htm
old-project: display
ms.assetid: 43e92a9e-e486-46d9-9eca-3db4ceeb24f1
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT
req.alt-loc: D3dumddi.h
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
req.iface: 
---

# D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT enumeration



## -description
<p>Identifies the overlay plane's video frame format. Only the <b>D3DDDI_MULIIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE</b> value is supported.</p>


## -syntax

````
typedef enum D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT { 
  D3DDDI_MULIIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE                    = 0,
  D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST     = 1,
  D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST  = 2
} D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT;
````


## -enum-fields
<dl>

### -field D3DDDI_MULIIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE

<dd>
<p>Progressive scan format.</p>
</dd>

### -field D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST

<dd>
<p>Reserved for system use. Do not use in your driver.</p>
</dd>

### -field D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST

<dd>
<p>Reserved for system use. Do not use in your driver.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>