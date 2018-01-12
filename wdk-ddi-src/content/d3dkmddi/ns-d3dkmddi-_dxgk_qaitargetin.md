---
UID: NS:d3dkmddi._DXGK_QAITARGETIN
title: _DXGK_QAITARGETIN
author: windows-driver-content
description: Used to integrate a target.
old-location: display\dxgk_qaitargetin.htm
old-project: display
ms.assetid: C6751CB1-1460-4C1A-9E5F-99448C4F9162
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_QAITARGETIN, DXGK_QAITARGETIN, DXGK_QUERYCOLORIMETRYOVERRIDESIN, DXGK_QUERYINTEGRATEDDISPLAYIN
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
req.alt-api: DXGK_QAITARGETIN
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
req.typenames: DXGK_QAITARGETIN
---

# _DXGK_QAITARGETIN structure



## -description
Used to integrate a target.



## -syntax

````
typedef struct _DXGK_QAITARGETIN {
  D3DDDI_VIDEO_PRESENT_TARGET_ID TargetId;
} DXGK_QAITARGETIN;
````


## -struct-fields

### -field TargetId

The ID of the target.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>