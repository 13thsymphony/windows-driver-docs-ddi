---
UID: NS:d3dkmddi._DXGK_QUERYSEGMENTMEMORYSTATE
title: "_DXGK_QUERYSEGMENTMEMORYSTATE"
author: windows-driver-content
description: DXGK_QUERYSEGMENTMEMORYSTATE is used with DxgkDdiQueryAdapterInfo to query invalid graphics processing unit (GPU) memory ranges.
old-location: display\dxgk_querysegmentmemorystate.htm
old-project: display
ms.assetid: 565D8D8D-6EBB-4303-8F7E-E2A4B1DAE4EA
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_QUERYSEGMENTMEMORYSTATE, DXGK_QUERYSEGMENTMEMORYSTATE structure [Display Devices], DXGK_SEGMENTMEMORYSTATE, _DXGK_QUERYSEGMENTMEMORYSTATE, d3dkmddi/DXGK_QUERYSEGMENTMEMORYSTATE, display.dxgk_querysegmentmemorystate
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
-	DXGK_QUERYSEGMENTMEMORYSTATE
product: Windows
targetos: Windows
req.typenames: DXGK_QUERYSEGMENTMEMORYSTATE, DXGK_SEGMENTMEMORYSTATE
---

# _DXGK_QUERYSEGMENTMEMORYSTATE structure
<b>DXGK_QUERYSEGMENTMEMORYSTATE</b> is used with <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> to query invalid graphics processing unit (GPU) memory ranges.

## Syntax
````
typedef struct _DXGK_QUERYSEGMENTMEMORYSTATE {
  WORD             DriverSegmentId;
  WORD             PhysicalAdapterIndex;
  UINT             NumInvalidMemoryRanges;
  DXGK_MEMORYRANGE *pMemoryRanges;
} DXGK_QUERYSEGMENTMEMORYSTATE;
````

## Members


`DriverSegmentId`

A  1-based segment identifier of a local GPU memory segment.

`PhysicalAdapterIndex`

Physical adapter index in a linked display adapter link.

`NumInvalidMemoryRanges`

The number of entries in the <b>pMemoryRanges</b> array. This is the value returned by the kernel mode driver in <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentdescriptor4.md">DXGK_SEGMENTDESCRIPTOR4</a>.

`pMemoryRanges`

Array of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_memoryrange.md">DXGK_MEMORYRANGE</a> structures for the invalid memory ranges.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentdescriptor4.md">DXGK_SEGMENTDESCRIPTOR4</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_memoryrange.md">DXGK_MEMORYRANGE</a>