---
UID: NS:d3dkmddi._DXGKARG_RENDERGDI
title: "_DXGKARG_RENDERGDI"
author: windows-driver-content
description: The DXGKARG_RENDERGDI structure is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing.
old-location: display\dxgkarg_rendergdi.htm
old-project: display
ms.assetid: E1DC536B-581E-43F8-99B2-776DC30EEBB7
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DXGKARG_RENDERGDI structure [Display Devices], _DXGKARG_RENDERGDI, d3dkmddi/DXGKARG_RENDERGDI, *INOUT_PDXGKARG_RENDERGDI, display.dxgkarg_rendergdi, DXGKARG_RENDERGDI
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_RENDERGDI
product: Windows
targetos: Windows
req.typenames: DXGKARG_RENDERGDI
---

# _DXGKARG_RENDERGDI structure
The <b>DXGKARG_RENDERGDI</b> structure is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing.

## Syntax
````
typedef struct _DXGKARG_RENDERGDI {
  const  VOID CONST      *pCommand;
  const UINT             CommandLength;
  VOID                   *pDmaBuffer;
  D3DGPU_VIRTUAL_ADDRESS DmaBufferGpuVirtualAddress;
  UINT                   DmaSize;
  VOID                   *pDmaBufferPrivateData;
  UINT                   DmaBufferPrivateDataSize;
  DXGK_ALLOCATIONLIST    *pAllocationList;
  UINT                   AllocationListSize;
  UINT                   MultipassOffset;
} DXGKARG_RENDERGDI;
````

## Members


`AllocationListSize`

The available number of elements in the array that <b>pAllocationList</b> specifies, which represents the number of allocation specifications to send through DMA to the graphics hardware.

`CommandLength`

The size, in bytes, of the command buffer that <b>pCommand</b> points to.

`DmaBufferGpuVirtualAddress`

A <b>D3DGPU_VIRTUAL_ADDRESS</b> data type that indicates the virtual address where the DMA buffer was paged in. If the physical address is zero, the DMA buffer is not correctly paged in.

`DmaBufferPrivateDataSize`

The number of bytes that remain in the private data structure that <b>pDmaBufferPrivateData</b> points to for the current operation.

`DmaSize`

The size, in bytes, of the DMA buffer that <b>pDmaBuffer</b> points to.

`MultipassOffset`

A value that specifies the progress of the rendering operation.

`pAllocationList`

An array of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationlist.md">DXGK_ALLOCATIONLIST</a> structures for the list of allocations that the DMA buffer references. Each allocation that is referenced should appear once for optimal performance.

`pCommand`

A pointer to the start of the command buffer.

`pDmaBuffer`

A pointer to the start of the DMA buffer, which is aligned on 4 KB.

`pDmaBufferPrivateData`

A pointer to a driver-resident private data structure that is used for generating the DMA buffer that <b>pDmaBuffer</b> points to.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |