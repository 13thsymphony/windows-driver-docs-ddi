---
UID: NS:d3dkmddi._DXGK_UPDATEPAGETABLEFLAGS
title: "_DXGK_UPDATEPAGETABLEFLAGS"
author: windows-driver-content
description: DXGK_UPDATEPAGETABLEFLAGS is used as part of a page table update operation.
old-location: display\dxgk_updatepagetableflags.htm
old-project: display
ms.assetid: E0E1CDE7-F1BF-44C8-A320-9BD90788679F
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_UPDATEPAGETABLEFLAGS, DXGK_UPDATEPAGETABLEFLAGS structure [Display Devices], _DXGK_UPDATEPAGETABLEFLAGS, d3dkmddi/DXGK_UPDATEPAGETABLEFLAGS, display.dxgk_updatepagetableflags
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_UPDATEPAGETABLEFLAGS
product:
- Windows
targetos: Windows
req.typenames: DXGK_UPDATEPAGETABLEFLAGS
---

# _DXGK_UPDATEPAGETABLEFLAGS structure
<b>DXGK_UPDATEPAGETABLEFLAGS</b> is used as part of a page table update operation.

## Syntax
```
typedef struct _DXGK_UPDATEPAGETABLEFLAGS {
  UINT  : 1  Repeat;
  UINT  : 1  InitialUpdate;
  UINT  : 1  NotifyEviction;
  UINT  : 1  Use64KBPages;
  UINT  : 28 Reserved;
} DXGK_UPDATEPAGETABLEFLAGS;
```

## Members


`Repeat`

When set to <b>TRUE</b>, page table entries will point to a single page table entry value that needs to be replicated to all page table entries being updated.

`InitialUpdate`

Indicates that the page table is initialized very first time after being made resident in memory.

`NotifyEviction`

Indicates that the page table is about to be evicted.

`Use64KBPages`

Indicates that page table entries  point to page tables pointing to 64 KB pages.

`Reserved`

This member is reserved and should be set to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |