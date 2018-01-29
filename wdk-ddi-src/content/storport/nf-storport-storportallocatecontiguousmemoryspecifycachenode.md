---
UID : NF:storport.StorPortAllocateContiguousMemorySpecifyCacheNode
title : StorPortAllocateContiguousMemorySpecifyCacheNode function
author : windows-driver-content
description : The StorPortAllocateContiguousMemorySpecifyCacheNode routine allocates a range of physically contiguous noncached, nonpaged memory.
old-location : storage\storportallocatecontiguousmemoryspecifycachenode.htm
old-project : storage
ms.assetid : b2ed8c88-9ffd-4601-8fd0-c9390e9ba84d
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : StorPortAllocateContiguousMemorySpecifyCacheNode routine [Storage Devices], storage.storportallocatecontiguousmemoryspecifycachenode, StorPortAllocateContiguousMemorySpecifyCacheNode, storport/StorPortAllocateContiguousMemorySpecifyCacheNode, storprt_d91d6ab4-677e-4bc0-a0b5-1c252475ecbb.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : storport.h
req.include-header : Storport.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 7.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : StorPortIrql
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
---


# StorPortAllocateContiguousMemorySpecifyCacheNode function
The <b>StorPortAllocateContiguousMemorySpecifyCacheNode</b> routine allocates a range of physically contiguous noncached, nonpaged memory.

## Syntax

````
ULONG StorPortAllocateContiguousMemorySpecifyCacheNode(
  _In_     PVOID               HwDeviceExtension,
  _In_     SIZE_T              NumberOfBytes,
  _In_     PHYSICAL_ADDRESS    LowestAcceptableAddress,
  _In_     PHYSICAL_ADDRESS    HighestAcceptableAddress,
  _In_opt_ PHYSICAL_ADDRESS    BoundaryAddressMultiple,
  _In_     MEMORY_CACHING_TYPE CacheType,
  _In_     NODE_REQUIREMENT    PreferredNode,
  _Out_    PVOID               *BufferPointer
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`NumberOfBytes`

The number of bytes to allocate.

`LowestAcceptableAddress`

The lowest physical address that is valid for the allocation. For example, if the device can only reference physical memory in the 8 MB to 16 MB range, this value would be set to 0x800000 (8 MB).

`HighestAcceptableAddress`

The highest physical address that is valid for the allocation. For example, if the device can only reference physical memory below 16 MB, this value would be set to 0xFFFFFF (16 MB - 1).

`BoundaryAddressMultiple`

The physical address multiple that this allocation must not cross.

`CacheType`

The desired cache type for the mapping.

`PreferredNode`

The preferred node from which the allocation should be made if pages are available on that node.

`BufferPointer`

The variable that receives the starting address of the allocated memory block. Upon return from this routine, if this variable is zero, a contiguous range could not be found to satisfy the request. If this variable is not <b>NULL</b>, it contains a pointer (for example, a virtual address in the nonpaged portion of the system) to the allocated physically contiguous memory.


## Return Value

The <b>StorPortAllocateContiguousMemorySpecifyCacheNode</b> routine returns one of the following status codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operation failed to allocate the requested memory because of insufficient resources.

</td>
</tr>
</table>

## Remarks

If the request fails, <i>BufferPointer</i> will be set to <b>NULL</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | StorPortIrql |