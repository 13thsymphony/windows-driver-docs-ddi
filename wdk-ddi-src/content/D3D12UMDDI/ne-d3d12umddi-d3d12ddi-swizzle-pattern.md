---
UID: NE.d3d12umddi.D3D12DDI_SWIZZLE_PATTERN
title: D3D12DDI_SWIZZLE_PATTERN
author: windows-driver-content
description: Specifies a swizzle pattern.
old-location: display\d3d12ddi_swizzle_pattern.htm
ms.assetid: 2C51BB44-3204-4EE8-9C86-605698BD58C0
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: display
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_SWIZZLE_PATTERN
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
ms.keywords: D3DWDDM2_2DDI_SWIZZLE_PATTERN_DESC, D3DWDDM2_2DDI_SWIZZLE_PATTERN_DESC
req.iface: 
---

# D3D12DDI_SWIZZLE_PATTERN enumeration



## -description
<p>Specifies a swizzle pattern.</p>


## -syntax

````
typedef enum D3D12DDI_SWIZZLE_PATTERN { 
  D3D12DDI_SP_ROW_MAJOR              = 0,
  D3D12DDI_SP_64KB_STANDARD_SWIZZLE  = 3,
  D3D12DDI_SP_DEVICE_DEPENDENT_0     = 0x100
} D3D12DDI_SWIZZLE_PATTERN;
````


## -enum-fields
<dl>

### -field <a id="D3D12DDI_SP_ROW_MAJOR"></a><a id="d3d12ddi_sp_row_major"></a><b>D3D12DDI_SP_ROW_MAJOR</b>

<dd>
<p>A row major swizzle pattern.</p>
</dd>

### -field <a id="D3D12DDI_SP_64KB_STANDARD_SWIZZLE"></a><a id="d3d12ddi_sp_64kb_standard_swizzle"></a><b>D3D12DDI_SP_64KB_STANDARD_SWIZZLE</b>

<dd>
<p>A 64 KB standard swizzle pattern.</p>
</dd>

### -field <a id="D3D12DDI_SP_DEVICE_DEPENDENT_0"></a><a id="d3d12ddi_sp_device_dependent_0"></a><b>D3D12DDI_SP_DEVICE_DEPENDENT_0</b>

<dd>
<p>A device dependant swizzle pattern. </p>
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
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>