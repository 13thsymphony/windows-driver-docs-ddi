---
UID: NS.D3DKMTHK._D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS
title: _D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS
author: windows-driver-content
description: Contains information about all possible brightness levels that an integrated display panel supports.
old-location: display\d3dkmt_brightness_possible_levels.htm
old-project: display
ms.assetid: d7402839-2afe-43d3-9747-7b2e98d1c238
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS, D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS
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
---

# _D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS structure



## -description
Contains information about all possible brightness levels that an integrated display panel supports.


## -syntax

````
typedef struct _D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS {
  UCHAR LevelCount;
  UCHAR BrightnessLevels[256];
} D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS;
````


## -struct-fields

### -field LevelCount

The number of brightness levels that the integrated display panel supports.

### -field BrightnessLevels

The specific brightness levels that the integrated display panel supports.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>