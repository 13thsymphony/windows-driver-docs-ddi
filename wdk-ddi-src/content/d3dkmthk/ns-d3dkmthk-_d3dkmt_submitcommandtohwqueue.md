---
UID: NS.D3DKMTHK._D3DKMT_SUBMITCOMMANDTOHWQUEUE
title: _D3DKMT_SUBMITCOMMANDTOHWQUEUE
author: windows-driver-content
description: A structure that holds information to submit a command to the hardware queue.
old-location: display\d3dkmt_submitcommandtohwqueue.htm
old-project: display
ms.assetid: 3807BD27-FAE4-4E12-A825-A9FAFB7A6ACA
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DKMT_SUBMITCOMMANDTOHWQUEUE, D3DKMT_SUBMITCOMMANDTOHWQUEUE
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
req.alt-api: D3DKMT_SUBMITCOMMANDTOHWQUEUE
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

# _D3DKMT_SUBMITCOMMANDTOHWQUEUE structure



## -description
A structure that holds information to submit a command to the hardware queue.


## -syntax

````
typedef struct _D3DKMT_SUBMITCOMMANDTOHWQUEUE {
  D3DKMT_HANDLE          hHwQueue;
  UINT64                 HwQueueProgressFenceId;
  D3DGPU_VIRTUAL_ADDRESS  CommandBuffer;
  UINT                   CommandLength;
  UINT                   PrivateDriverDataSize;
  VOID                   *pPrivateDriverData;
  UINT                   NumPrimaries;
  D3DKMT_HANDLE CONST    *WrittenPrimaries;
} D3DKMT_SUBMITCOMMANDTOHWQUEUE;
````


## -struct-fields

### -field hHwQueue

Context queue to submit the command to.


### -field HwQueueProgressFenceId

Hardware queue progress fence value that will be signaled once the command is finished.

### -field  CommandBuffer

GPU VA of the command buffer to be executed on the GPU.


### -field CommandLength

Length in bytes of the command buffer.



### -field PrivateDriverDataSize

Size of private driver data in bytes.



### -field pPrivateDriverData

Pointer to the private driver data.


### -field NumPrimaries

The number of primaries written by this command buffer.


### -field WrittenPrimaries

The array of primaries written by this command buffer.


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