---
UID: NE.d3d12umddi.D3D12DDI_PREDICATION_OP
title: D3D12DDI_PREDICATION_OP
author: windows-driver-content
description: Contains values for predication operation options.
old-location: display\d3d12ddi_predication_op.htm
old-project: display
ms.assetid: 70676251-BCD7-4996-B5B7-96A8D9B107DB
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: D3D12DDI_PREDICATION_OP, D3D12DDI_PREDICATION_OP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_PREDICATION_OP
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

# D3D12DDI_PREDICATION_OP enumeration



## -description
Contains values for predication operation options. 


## -syntax

````
typedef enum D3D12DDI_PREDICATION_OP { 
  D3D12DDI_PREDICATION_OP_EQUAL_ZERO      = 0,
  D3D12DDI_PREDICATION_OP_NOT_EQUAL_ZERO  = 1
} D3D12DDI_PREDICATION_OP;
````


## -enum-fields

### -field D3D12DDI_PREDICATION_OP_EQUAL_ZERO

All the bits in a 64 bit buffer are zero (0).

### -field D3D12DDI_PREDICATION_OP_NOT_EQUAL_ZERO

Not all of the bits in a 64 bit buffer are zero (0).

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