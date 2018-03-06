---
UID: NS:d3dumddi._D3DDDICB_CREATEHWQUEUE
title: "_D3DDDICB_CREATEHWQUEUE"
author: windows-driver-content
description: A structure that holds information to create a hardware queue.
old-location: display\d3dddicb_createhwqueue.htm
old-project: display
ms.assetid: 085CEF61-2C2E-4F9C-B143-2E2D58C51643
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICB_CREATEHWQUEUE, D3DDDICB_CREATEHWQUEUE structure [Display Devices], _D3DDDICB_CREATEHWQUEUE, d3dumddi/D3DDDICB_CREATEHWQUEUE, display.d3dddicb_createhwqueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDICB_CREATEHWQUEUE
product: Windows
targetos: Windows
req.typenames: D3DDDICB_CREATEHWQUEUE
---

# _D3DDDICB_CREATEHWQUEUE structure
A structure that holds information to create a hardware queue.

## Syntax
````
typedef struct _D3DDDICB_CREATEHWQUEUE {
  HANDLE                     hHwContext;
  D3DDDI_CREATEHWQUEUEFLAGS Flags;
  UINT                      PrivateDriverDataSize;
  VOID                      *pPrivateDriverData;
   HANDLE                   hHwQueue;
  D3DKMT_HANDLE             hHwQueueProgressFence;
  VOID                      *HwQueueProgressFenceCPUVirtualAddress;
  D3DGPU_VIRTUAL_ADDRESS    HwQueueProgressFenceGPUVirtualAddress;
} D3DDDICB_CREATEHWQUEUE;
````

## Members


`Flags`

Queue creation flags.

`hHwContext`

Handle to the context the queue is created for.

`hHwQueue`

Handle to the created queue.

`hHwQueueProgressFence`

Handle to the hardware queue progress fence object.

`HwQueueProgressFenceCPUVirtualAddress`

Read-only mapping of the fence value for the CPU

`HwQueueProgressFenceGPUVirtualAddress`

Read/write mapping of the fence value for the GPU

`pPrivateDriverData`

Pointer to private driver data.

`PrivateDriverDataSize`

Size of private driver data.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dumddi.h |