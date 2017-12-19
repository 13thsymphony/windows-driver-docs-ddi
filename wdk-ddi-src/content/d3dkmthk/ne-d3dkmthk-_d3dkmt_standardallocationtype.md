---
UID: NE.d3dkmthk._D3DKMT_STANDARDALLOCATIONTYPE
title: _D3DKMT_STANDARDALLOCATIONTYPE
author: windows-driver-content
description: Used to give information on the allocation type.
old-location: display\d3dkmt-standardallocationtype.htm
old-project: display
ms.assetid: 7ce6d148-bfe8-4040-a4c1-ccd22fd07307
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMT_STANDARDALLOCATIONTYPE, D3DKMT_STANDARDALLOCATIONTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_STANDARDALLOCATIONTYPE
req.alt-loc: d3dkmthk.h
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

# _D3DKMT_STANDARDALLOCATIONTYPE enumeration



## -description
Used to give information on the allocation type.



## -syntax

````
typedef enum _D3DKMT_STANDARDALLOCATIONTYPE { 
  D3DKMT_STANDARDALLOCATIONTYPE_EXISTINGHEAP  = 1
} D3DKMT_STANDARDALLOCATIONTYPE;
````


## -enum-fields

### -field D3DKMT_STANDARDALLOCATIONTYPE_EXISTINGHEAP

Indicates that the allocation type is an existing heap.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h</dt>
</dl>
</td>
</tr>
</table>