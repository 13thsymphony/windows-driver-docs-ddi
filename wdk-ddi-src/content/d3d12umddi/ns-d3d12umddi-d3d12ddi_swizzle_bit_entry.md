---
UID: NS.D3D12UMDDI.D3D12DDI_SWIZZLE_BIT_ENTRY
title: D3D12DDI_SWIZZLE_BIT_ENTRY
author: windows-driver-content
description: Defines a swizzle bit entry.
old-location: display\d3d12ddi_swizzle_bit_entry.htm
old-project: display
ms.assetid: B7FF7AA2-39B2-4D9E-8DDC-0A39FFF49F37
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: D3D12DDI_SWIZZLE_BIT_ENTRY, D3D12DDI_SWIZZLE_BIT_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_SWIZZLE_BIT_ENTRY
req.alt-loc: D3d12umddi.h
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

# D3D12DDI_SWIZZLE_BIT_ENTRY structure



## -description
Defines a swizzle bit entry.


## -syntax

````
typedef struct D3D12DDI_SWIZZLE_BIT_ENTRY {
  UINT8 Valid  :1;
  UINT8 ChannelIndex  :2;
  UINT8 SourceBitIndex  :5;
} D3D12DDI_SWIZZLE_BIT_ENTRY;
````


## -struct-fields

### -field Valid

A valid value.

### -field ChannelIndex

The channel index. Specify zero (0) for X, one (1) for Y, two (2) for Z, and three (3) for SS.

### -field SourceBitIndex

Index of source bit address.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>