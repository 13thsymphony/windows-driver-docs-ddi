---
UID: NE.d3dkmdt._D3DKMDT_MONITOR_DESCRIPTOR_TYPE
title: _D3DKMDT_MONITOR_DESCRIPTOR_TYPE
author: windows-driver-content
description: The D3DKMDT_MONITOR_DESCRIPTOR_TYPE enumeration is used to indicate a particular type of monitor descriptor.
old-location: display\d3dkmdt_monitor_descriptor_type.htm
old-project: display
ms.assetid: f5ec761f-fc20-4baf-a012-c32356644a6c
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DKMDT_MONITOR_DESCRIPTOR_TYPE, D3DKMDT_MONITOR_DESCRIPTOR_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_MONITOR_DESCRIPTOR_TYPE
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

# _D3DKMDT_MONITOR_DESCRIPTOR_TYPE enumeration



## -description
The D3DKMDT_MONITOR_DESCRIPTOR_TYPE enumeration is used to indicate a particular type of monitor descriptor.



## -syntax

````
typedef enum _D3DKMDT_MONITOR_DESCRIPTOR_TYPE { 
  D3DKMDT_MDT_UNINITIALIZED           = 0,
  D3DKMDT_MDT_VESA_EDID_V1_BASEBLOCK  = 1,
  D3DKMDT_MDT_VESA_EDID_V1_BLOCKMAP   = 2,
  D3DKMDT_MDT_OTHER                   = 255
} D3DKMDT_MONITOR_DESCRIPTOR_TYPE;
````


## -enum-fields

### -field D3DKMDT_MDT_UNINITIALIZED

Indicates that a variable of type D3DKMDT_MONITOR_DESCRIPTOR_TYPE has not yet been assigned a meaningful value.


### -field D3DKMDT_MDT_VESA_EDID_V1_BASEBLOCK

Indicates that the descriptor is an Extended Display Identification Data (EDID) base block.


### -field D3DKMDT_MDT_VESA_EDID_V1_BLOCKMAP

Indicates that the descriptor is an EDID block map.


### -field D3DKMDT_MDT_OTHER

Indicates that the descriptor has a type other than those indicated by the previous values of this enumeration.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>