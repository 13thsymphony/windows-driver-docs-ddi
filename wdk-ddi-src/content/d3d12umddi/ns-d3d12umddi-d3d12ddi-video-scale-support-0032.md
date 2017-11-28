---
UID: NS.d3d12umddi.D3D12DDI_VIDEO_SCALE_SUPPORT_0032
title: D3D12DDI_VIDEO_SCALE_SUPPORT_0032
author: windows-driver-content
description: Video scale support.
old-location: display\d3d12ddi-video-scale-support-0032.htm
old-project: display
ms.assetid: 630ee3fe-f97a-4e82-83d7-4efd05bc5d6e
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D12DDI_VIDEO_SCALE_SUPPORT_0032, D3D12DDI_VIDEO_SCALE_SUPPORT_0032
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_VIDEO_SCALE_SUPPORT_0032
req.alt-loc: d3d12umddi.h
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

# D3D12DDI_VIDEO_SCALE_SUPPORT_0032 structure



## -description
<p>Video scale support.</p>


## -syntax

````
typedef struct _D3D12DDI_VIDEO_SCALE_SUPPORT_0032 {
  D3D12DDI_VIDEO_SIZE_RANGE_0032           OutputSizeRange;
  D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022  Flags;
} D3D12DDI_VIDEO_SCALE_SUPPORT_0032, D3D12DDI_VIDEO_SCALE_SUPPORT_0032;
````


## -struct-fields
<dl>

### -field <b>OutputSizeRange</b>

<dd>
<p>Output size range.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>Flags.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>