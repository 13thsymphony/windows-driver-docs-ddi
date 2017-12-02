---
UID: NS.d3dkmthk._D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS
title: D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS
author: windows-driver-content
description: Contains information about all possible brightness levels that an integrated display panel supports.
old-location: display\d3dkmt_brightness_possible_levels.htm
old-project: display
ms.assetid: d7402839-2afe-43d3-9747-7b2e98d1c238
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS, D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS
req.alt-loc: D3dkmthk.h
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

# D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS structure



## -description
<p>Contains information about all possible brightness levels that an integrated display panel supports.</p>


## -syntax

````
typedef struct _D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS {
  UCHAR LevelCount;
  UCHAR BrightnessLevels[256];
} D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS;
````


## -struct-fields
<dl>

### -field LevelCount

<dd>
<p>The number of brightness levels that the integrated display panel supports.</p>
</dd>

### -field BrightnessLevels

<dd>
<p>The specific brightness levels that the integrated display panel supports.</p>
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
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>