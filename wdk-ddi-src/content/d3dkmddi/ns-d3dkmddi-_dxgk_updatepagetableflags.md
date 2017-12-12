---
UID: NS.D3DKMDDI._DXGK_UPDATEPAGETABLEFLAGS
title: _DXGK_UPDATEPAGETABLEFLAGS
author: windows-driver-content
description: DXGK_UPDATEPAGETABLEFLAGS is used as part of a page table update operation.
old-location: display\dxgk_updatepagetableflags.htm
old-project: display
ms.assetid: E0E1CDE7-F1BF-44C8-A320-9BD90788679F
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_UPDATEPAGETABLEFLAGS, DXGK_UPDATEPAGETABLEFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_UPDATEPAGETABLEFLAGS
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

# _DXGK_UPDATEPAGETABLEFLAGS structure



## -description
<b>DXGK_UPDATEPAGETABLEFLAGS</b> is used as part of a page table update operation.



## -syntax

````
typedef struct _DXGK_UPDATEPAGETABLEFLAGS {
  UINT Repeat  :1;
  UINT InitialUpdate  :1;
  UINT NotifyEviction  :1;
  UINT Use64KBPages  :1;
  UINT Reserved  :28;
} DXGK_UPDATEPAGETABLEFLAGS;
````


## -struct-fields

### -field Repeat

When set to <b>TRUE</b>, page table entries will point to a single page table entry value that needs to be replicated to all page table entries being updated.


### -field InitialUpdate

Indicates that the page table is initialized very first time after being made resident in memory.


### -field NotifyEviction

Indicates that the page table is about to be evicted. 


### -field Use64KBPages

Indicates that page table entries  point to page tables pointing to 64 KB pages. 


### -field Reserved

This member is reserved and should be set to zero.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>