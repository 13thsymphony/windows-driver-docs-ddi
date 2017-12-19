---
UID: NE.d3dukmdt._DXGKVGPU_ESCAPE_TYPE
title: _DXGKVGPU_ESCAPE_TYPE
author: windows-driver-content
description: An enum that holds information about the escape type.
old-location: display\dxgkvgpu_escape_type.htm
old-project: display
ms.assetid: F7081B59-DB24-4BFE-B1BD-3BE228804AB2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGKVGPU_ESCAPE_TYPE, DXGKVGPU_ESCAPE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKVGPU_ESCAPE_TYPE
req.alt-loc: d3dukmdt.h
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

# _DXGKVGPU_ESCAPE_TYPE enumeration



## -description
An enum that holds information about the escape type.



## -syntax

````
typedef enum _DXGKVGPU_ESCAPE_TYPE { 
  DXGKVGPU_ESCAPE_TYPE_READ_PCI_CONFIG  = 0,
  DXGKVGPU_ESCAPE_TYPE_GET_VGPU_TYPE    = 4
} DXGKVGPU_ESCAPE_TYPE;
````


## -enum-fields

### -field DXGKVGPU_ESCAPE_TYPE_READ_PCI_CONFIG

Indicates the PCI config of the escape type.


### -field DXGKVGPU_ESCAPE_TYPE_GET_VGPU_TYPE

Indicates the VGPU type of the escape.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dukmdt.h</dt>
</dl>
</td>
</tr>
</table>