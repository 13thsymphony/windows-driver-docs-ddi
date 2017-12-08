---
UID: NS.D3DUMDDI._D3DDDICB_CREATEHWQUEUE
title: _D3DDDICB_CREATEHWQUEUE
author: windows-driver-content
description: A structure that holds information to create a hardware queue.
old-location: display\d3dddicb_createhwqueue.htm
old-project: display
ms.assetid: 085CEF61-2C2E-4F9C-B143-2E2D58C51643
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDICB_CREATEHWQUEUE, D3DDDICB_CREATEHWQUEUE
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
req.alt-api: D3DDDICB_CREATEHWQUEUE
req.alt-loc: d3dumddi.h
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

# _D3DDDICB_CREATEHWQUEUE structure



## -description
A structure that holds information to create a hardware queue.


## -syntax

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


## -struct-fields

### -field  hHwContext

Handle to the context the queue is created for.


### -field Flags

Queue creation flags.

### -field PrivateDriverDataSize

 Size of private driver data.

### -field pPrivateDriverData

Pointer to private driver data.

### -field hHwQueue

Handle to the created queue.

### -field hHwQueueProgressFence

Handle to the hardware queue progress fence object.


### -field HwQueueProgressFenceCPUVirtualAddress

Read-only mapping of the fence value for the CPU


### -field HwQueueProgressFenceGPUVirtualAddress

Read/write mapping of the fence value for the GPU


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h</dt>
</dl>
</td>
</tr>
</table>