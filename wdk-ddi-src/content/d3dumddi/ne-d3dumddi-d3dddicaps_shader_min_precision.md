---
UID: NE.d3dumddi.D3DDDICAPS_SHADER_MIN_PRECISION
title: D3DDDICAPS_SHADER_MIN_PRECISION
author: windows-driver-content
description: Specifies minimum precision levels that the user-mode driver supports in shaders.
old-location: display\d3dddicaps_shader_min_precision.htm
old-project: display
ms.assetid: 98856726-b426-42e4-9560-f6b56164824a
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3DDDICAPS_SHADER_MIN_PRECISION, D3DDDICAPS_SHADER_MIN_PRECISION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICAPS_SHADER_MIN_PRECISION
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
---

# D3DDDICAPS_SHADER_MIN_PRECISION enumeration



## -description
Specifies minimum precision levels that the user-mode driver supports in shaders.



## -syntax

````
typedef enum D3DDDICAPS_SHADER_MIN_PRECISION { 
  D3DDDICAPS_SHADER_MIN_PRECISION_10_BIT  = 0x1,
  D3DDDICAPS_SHADER_MIN_PRECISION_16_BIT  = 0x2
} D3DDDICAPS_SHADER_MIN_PRECISION;
````


## -enum-fields

### -field D3DDDICAPS_SHADER_MIN_PRECISION_10_BIT

The minimum precision level is 10-bit.


### -field D3DDDICAPS_SHADER_MIN_PRECISION_16_BIT

The minimum precision level is 16-bit.


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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>