---
UID: NS:d3dkmddi._DXGKARG_SETROOTPAGETABLE
title: "_DXGKARG_SETROOTPAGETABLE"
author: windows-driver-content
description: DXGKARG_SETROOTPAGETABLE is used by the DxgkDdiSetRootPageTabledevice driver interface (DDI) to notify a context when its associated root page table is resized or moved in memory.
old-location: display\dxgkarg_setrootpagetable.htm
old-project: display
ms.assetid: D3863924-29EE-4886-B8DC-F9020A7C85A4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKARG_SETROOTPAGETABLE, DXGKARG_SETROOTPAGETABLE structure [Display Devices], _DXGKARG_SETROOTPAGETABLE, d3dkmddi/DXGKARG_SETROOTPAGETABLE, display.dxgkarg_setrootpagetable
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
-	DXGKARG_SETROOTPAGETABLE
product: Windows
targetos: Windows
req.typenames: DXGKARG_SETROOTPAGETABLE
---

# _DXGKARG_SETROOTPAGETABLE structure
<b>DXGKARG_SETROOTPAGETABLE</b> is used by the <a href="https://msdn.microsoft.com/BC9E7A2D-690D-4EC2-8D16-22C5FEBA574A">DxgkDdiSetRootPageTable</a>device driver interface (DDI) to notify a context when its associated root page table is resized or moved in memory.

## Syntax
```
typedef struct _DXGKARG_SETROOTPAGETABLE {
  HANDLE                  hContext;
  D3DGPU_PHYSICAL_ADDRESS Address;
  UINT                    NumEntries;
} DXGKARG_SETROOTPAGETABLE;
```

## Members


`hContext`

A context handle returned by <a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a>.

`Address`

The GPU physical address of the root page table.

`NumEntries`

The root page table size in entries. GPU should generate invalid fault when a virtual address has a top level page table entry index, which is greater or equal this value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a>



<a href="https://msdn.microsoft.com/BC9E7A2D-690D-4EC2-8D16-22C5FEBA574A">DxgkDdiSetRootPageTable</a>