---
UID: NE.d3dkmdt._DXGK_DISPLAY_DESCRIPTOR_TYPE
title: _DXGK_DISPLAY_DESCRIPTOR_TYPE
author: windows-driver-content
description: Enum used to express the display descriptor type.
old-location: display\dxgk_display_descriptor_type.htm
old-project: display
ms.assetid: 2AC0B5CF-67FB-462F-9118-E30FEDE9A019
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGK_DISPLAY_DESCRIPTOR_TYPE, *PDXGK_DISPLAY_DESCRIPTOR_TYPE, DXGK_DISPLAY_DESCRIPTOR_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_DISPLAY_DESCRIPTOR_TYPE
req.alt-loc: d3dkmdt.h
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

# _DXGK_DISPLAY_DESCRIPTOR_TYPE enumeration



## -description
Enum used to express the display descriptor type.


## -syntax

````
typedef enum _DXGK_DISPLAY_DESCRIPTOR_TYPE { 
  DXGK_DDT_INVALID  = 0,
  DXGK_DDT_EDID
} DXGK_DISPLAY_DESCRIPTOR_TYPE, *PDXGK_DISPLAY_DESCRIPTOR_TYPE ;
````


## -enum-fields

### -field DXGK_DDT_INVALID

Invalid type.

### -field DXGK_DDT_EDID

A VESA EDID descriptor.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h</dt>
</dl>
</td>
</tr>
</table>