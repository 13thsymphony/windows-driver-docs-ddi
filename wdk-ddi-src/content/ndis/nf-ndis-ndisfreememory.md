---
UID: NF:ndis.NdisFreeMemory
title: NdisFreeMemory function
author: windows-driver-content
description: The NdisFreeMemory function releases a block of memory that was previously allocated with the NdisAllocateMemoryWithTagPriority function.
old-location: netvista\ndisfreememory.htm
old-project: netvista
ms.assetid: 0096fef7-2a5a-45cd-8e54-dc1ec0e84237
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisFreeMemory, NdisFreeMemory function [Network Drivers Starting with Windows Vista], ndis/NdisFreeMemory, ndis_memory_ref_a178b0d7-8966-4356-8f63-3293605a6655.xml, netvista.ndisfreememory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisFreeMemory (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisFreeMemory (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function, NdisQueryBindInstanceName
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFreeMemory
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisFreeMemory function
The
  <b>NdisFreeMemory</b> function releases a block of memory that was previously allocated with the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff561606">NdisAllocateMemoryWithTagPriority</a> function.

## Syntax

```
void NdisFreeMemory(
  __drv_freesMem(Mem)PVOID VirtualAddress,
  UINT                     Length,
  UINT                     MemoryFlags
);
```

## Parameters

`VirtualAddress`

A pointer to the base virtual address of the allocated memory. This address was returned by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561606">NdisAllocateMemoryWithTagPriority</a> function.

`Length`

The size, in bytes, of the memory block to be released. If the memory was allocated with <a href="https://msdn.microsoft.com/library/windows/hardware/ff561606">NdisAllocateMemoryWithTagPriority</a> or the <i>MemoryFlags</i> parameter is zero, this parameter is ignored.

`MemoryFlags`

A set of flags that specify the type of memory to free. This value must be zero if the memory was
      allocated with 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff561606">NdisAllocateMemoryWithTagPriority</a>. With NDIS 6.0 and later versions, the 
      <b>NdisAllocateMemoryWithTagPriority</b> is always used to allocate memory.


## Return Value

None

## Remarks

Because noncached memory and contiguous memory are seldom released until the allocating miniport
    driver is unloading, a caller of 
    <b>NdisFreeMemory</b> usually is running at IRQL = PASSIVE_LEVEL for these types of deallocations. In any
    case:

<ul>
<li>
When releasing contiguous memory, a caller of 
      <b>NdisFreeMemory</b> must be running at IRQL = PASSIVE_LEVEL.

</li>
<li>
When releasing noncached memory, a caller of 
      <b>NdisFreeMemory</b> must be running at IRQL &lt; DISPATCH_LEVEL.

</li>
<li>
When releasing memory that is neither contiguous nor noncached, a caller of 
      <b>NdisFreeMemory</b> must be running at IRQL &lt;= DISPATCH_LEVEL.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisFreeMemory (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisFreeMemory (NDIS 5.1)) in   Windows XP.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | See Remarks section |
| **DDI compliance rules** | Irql_Miscellaneous_Function, NdisQueryBindInstanceName |

## See Also

<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/aac4049c-a876-4bbb-ba3b-fa36c299e1c7">
   NdisAllocateMemoryWithTagPriority</a>