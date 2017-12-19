---
UID: NS.D3DKMTHK._D3DKMT_CREATEHWQUEUE
title: _D3DKMT_CREATEHWQUEUE
author: windows-driver-content
description: A structure holding information to create a hardware queue.
old-location: display\d3dkmt_createhwqueue.htm
old-project: display
ms.assetid: DBD99353-4798-4540-89DB-EA08521B276E
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMT_CREATEHWQUEUE, D3DKMT_CREATEHWQUEUE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_CREATEHWQUEUE
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

# _D3DKMT_CREATEHWQUEUE structure



## -description
A structure holding information to create a hardware queue.



## -syntax

````
typedef struct _D3DKMT_CREATEHWQUEUE {
  D3DKMT_HANDLE             hHwContext;
  D3DDDI_CREATEHWQUEUEFLAGS Flags;
  UINT                      PrivateDriverDataSize;
  VOID                      *pPrivateDriverData;
  D3DKMT_HANDLE             hHwQueue;
  D3DKMT_HANDLE             hHwQueueProgressFence;
  VOID                      *HwQueueProgressFenceCPUVirtualAddress;
  D3DGPU_VIRTUAL_ADDRESS    HwQueueProgressFenceGPUVirtualAddress;
} D3DKMT_CREATEHWQUEUE;
````


## -struct-fields

### -field hHwContext

Handle to the hardware context the queue is associated with.



### -field Flags

Hardware queue creation flags.



### -field PrivateDriverDataSize

Size of private driver data.


### -field pPrivateDriverData

Private driver data.


### -field hHwQueue

Handle to the hardware queue object to submit work to.


### -field hHwQueueProgressFence

Handle to the monitored fence object used to monitor the queue progress.


### -field HwQueueProgressFenceCPUVirtualAddress

Read-only mapping of the queue progress fence value for the CPU.


### -field HwQueueProgressFenceGPUVirtualAddress

Read/write mapping of the queue progress fence value for the GPU.


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