---
UID: NS:d3dkmthk._D3DKMT_CREATEPAGINGQUEUE
title: "_D3DKMT_CREATEPAGINGQUEUE"
author: windows-driver-content
description: D3DKMT_CREATEPAGINGQUEUE is used with D3DKMTCreatePagingQueue to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.
old-location: display\d3dkmt_createpagingqueue.htm
old-project: display
ms.assetid: F7C2847F-D095-4A79-ADBB-DA0745E3192A
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_CREATEPAGINGQUEUE, D3DKMT_CREATEPAGINGQUEUE structure [Display Devices], _D3DKMT_CREATEPAGINGQUEUE, d3dkmthk/D3DKMT_CREATEPAGINGQUEUE, display.d3dkmt_createpagingqueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_CREATEPAGINGQUEUE
product: Windows
targetos: Windows
req.typenames: D3DKMT_CREATEPAGINGQUEUE
---

# _D3DKMT_CREATEPAGINGQUEUE structure
<b>D3DKMT_CREATEPAGINGQUEUE</b> is used with <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatepagingqueue.md">D3DKMTCreatePagingQueue</a> to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.

## Syntax
````
typedef struct _D3DKMT_CREATEPAGINGQUEUE {
  D3DKMT_HANDLE               hDevice;
  D3DDDI_PAGINGQUEUE_PRIORITY Priority;
  D3DKMT_HANDLE               hPagingQueue;
  D3DKMT_HANDLE               hSyncObject;
  VOID                        *FenceValueCPUVirtualAddress;
  UINT                        PhysicalAdapterIndex;
} D3DKMT_CREATEPAGINGQUEUE;
````

## Members


`hDevice`

[in] Device to create a new paging queue object for.

`Priority`

[in] Scheduling priority relative to other paging queues on this device. Paging queues with higher priority values will be processed ahead of paging queues with lower priority values.

`hPagingQueue`

[out] A paging queue handle that will be used to synchronize paging operations.

`hSyncObject`

[out] Handle to the monitored fence object used to synchronize paging operations for this paging queue. Destroying the paging queue (either implicitly or explicitly) will automatically destroy this sync object.

`FenceValueCPUVirtualAddress`

[out] A read-only mapping of the paging fence object value for the CPU. This is a user mode address readable from the process that created the monitored fence object.

`PhysicalAdapterIndex`

[in] Physical adapter index (engine ordinal) for the queue.

## Remarks
A device can have multiple paging queues created for it. Paging queues can be destroyed either explicitly by calling <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroypagingqueue.md">D3DKMTDestroyPagingQueue</a>, or by implicitly destroying the device they belong to. After the latter, paging queue handles will become invalid.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatepagingqueue.md">D3DKMTCreatePagingQueue</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroypagingqueue.md">D3DKMTDestroyPagingQueue</a>