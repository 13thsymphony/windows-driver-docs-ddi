---
UID: NS.D3DKMDDI._DXGK_QUERYDISPLAYIDOUT
title: _DXGK_QUERYDISPLAYIDOUT
author: windows-driver-content
description: Used to query a display ID.
old-location: display\dxgk_querydisplayidout.htm
old-project: display
ms.assetid: BF528089-0194-4A3F-B8BA-85F80974C4C2
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGK_QUERYDISPLAYIDOUT, DXGK_QUERYDISPLAYIDOUT
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
req.alt-api: DXGK_QUERYDISPLAYIDOUT
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
---

# _DXGK_QUERYDISPLAYIDOUT structure



## -description
Used to query a display ID.


## -syntax

````
typedef struct _DXGK_QUERYDISPLAYIDOUT {
  UINT Length;
  BYTE *pDescriptor;
} DXGK_QUERYDISPLAYIDOUT;
````


## -struct-fields

### -field Length

The length of the Display ID.

### -field pDescriptor

A pointer to the descriptor of the ID.

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