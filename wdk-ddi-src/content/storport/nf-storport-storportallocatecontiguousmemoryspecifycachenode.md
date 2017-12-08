---
UID: NF.storport.StorPortAllocateContiguousMemorySpecifyCacheNode
title: StorPortAllocateContiguousMemorySpecifyCacheNode function
author: windows-driver-content
description: The StorPortAllocateContiguousMemorySpecifyCacheNode routine allocates a range of physically contiguous noncached, nonpaged memory.
old-location: storage\storportallocatecontiguousmemoryspecifycachenode.htm
old-project: storage
ms.assetid: b2ed8c88-9ffd-4601-8fd0-c9390e9ba84d
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: StorPortAllocateContiguousMemorySpecifyCacheNode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortAllocateContiguousMemorySpecifyCacheNode
req.alt-loc: storport.h
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# StorPortAllocateContiguousMemorySpecifyCacheNode function



## -description
The <b>StorPortAllocateContiguousMemorySpecifyCacheNode</b> routine allocates a range of physically contiguous noncached, nonpaged memory.


## -syntax

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


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param NumberOfBytes [in]

The number of bytes to allocate.

### -param LowestAcceptableAddress [in]

The lowest physical address that is valid for the allocation. For example, if the device can only reference physical memory in the 8 MB to 16 MB range, this value would be set to 0x800000 (8 MB).

### -param HighestAcceptableAddress [in]

The highest physical address that is valid for the allocation. For example, if the device can only reference physical memory below 16 MB, this value would be set to 0xFFFFFF (16 MB - 1).

### -param BoundaryAddressMultiple [in, optional]

The physical address multiple that this allocation must not cross.

### -param CacheType [in]

The desired cache type for the mapping.

### -param PreferredNode [in]

The preferred node from which the allocation should be made if pages are available on that node.

### -param BufferPointer [out]

The variable that receives the starting address of the allocated memory block. Upon return from this routine, if this variable is zero, a contiguous range could not be found to satisfy the request. If this variable is not <b>NULL</b>, it contains a pointer (for example, a virtual address in the nonpaged portion of the system) to the allocated physically contiguous memory.

## -returns
The <b>StorPortAllocateContiguousMemorySpecifyCacheNode</b> routine returns one of the following status codes:
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This function is not implemented on the active operating system.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The operation was successful.
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The operation failed to allocate the requested memory because of insufficient resources.

 

## -remarks
If the request fails, <i>BufferPointer</i> will be set to <b>NULL</b>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows 7.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.storport_storportirql">StorPortIrql</a>
</td>
</tr>
</table>