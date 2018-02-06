---
UID: NF:wdm.MmAllocateNodePagesForMdlEx
title: MmAllocateNodePagesForMdlEx function
author: windows-driver-content
description: The MmAllocateNodePagesForMdlEx routine allocates nonpaged physical memory from an ideal node, and allocates an MDL structure to describe this memory.
old-location: kernel\mmallocatenodepagesformdlex.htm
old-project: kernel
ms.assetid: 491327A4-87B5-4206-9D47-007CE14E1327
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: MmAllocateNodePagesForMdlEx routine [Kernel-Mode Driver Architecture], kernel.mmallocatenodepagesformdlex, wdm/MmAllocateNodePagesForMdlEx, MmAllocateNodePagesForMdlEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL (See Remarks section.)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmAllocateNodePagesForMdlEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# MmAllocateNodePagesForMdlEx function
The <b>MmAllocateNodePagesForMdlEx</b> routine allocates nonpaged physical memory from an ideal node, and allocates an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> structure to describe this memory.

## Syntax

````
PMDL MmAllocateNodePagesForMdlEx(
  _In_ PHYSICAL_ADDRESS    LowAddress,
  _In_ PHYSICAL_ADDRESS    HighAddress,
  _In_ PHYSICAL_ADDRESS    SkipBytes,
  _In_ SIZE_T              TotalBytes,
  _In_ MEMORY_CACHING_TYPE CacheType,
  _In_ ULONG               IdealNode,
  _In_ ULONG               Flags
);
````

## Parameters

`LowAddress`

The physical address of the start of the first address range from which the allocated pages can come. If <b>MmAllocateNodePagesForMdlEx</b> cannot allocate the requested number of bytes in the first address range, the routine iterates through additional address ranges to get more pages. At each iteration, <b>MmAllocateNodePagesForMdlEx</b> adds the value of <i>SkipBytes</i> to the previous start address to calculate the start of the next address range.

`HighAddress`

The physical address of the end of the first address range that the allocated pages can come from.

`SkipBytes`

The number of bytes to skip from the start of the previous address range that the allocated pages can come from. <i>SkipBytes</i> must be an integer multiple of the virtual memory page size, in bytes.

`TotalBytes`

The total number of bytes to allocate for the MDL.

`CacheType`

A <a href="..\wdm\ne-wdm-_memory_caching_type.md">MEMORY_CACHING_TYPE</a> value, which indicates the type of caching that is allowed for the requested memory.

`IdealNode`

The ideal node number. If a multiprocessor system contains N nodes, valid node numbers are in the range 0 to N-1. Your driver can call the <a href="..\wdm\nf-wdm-kequeryhighestnodenumber.md">KeQueryHighestNodeNumber</a> routine to get the highest node number. A single-processor or non-NUMA multiprocessor system has only one node, node 0, from which to allocate memory. For a NUMA multiprocessor system, the allocation is made from the ideal node, if possible. If insufficient memory is available in the ideal node to satisfy the allocation request, and the caller does not set the MM_ALLOCATE_FROM_LOCAL_NODE_ONLY flag, <b>MmAllocateNodePagesForMdlEx</b> will try to allocate memory from other nodes.

`Flags`

Flags for this operation. Set this parameter to zero or to the bitwise-OR of one or more of the following flag bits:
<ul>
<li>
MM_DONT_ZERO_ALLOCATION

</li>
<li>
MM_ALLOCATE_FROM_LOCAL_NODE_ONLY

</li>
<li>
MM_ALLOCATE_FULLY_REQUIRED

</li>
<li>
MM_ALLOCATE_NO_WAIT

</li>
<li>
MM_ALLOCATE_PREFER_CONTIGUOUS

</li>
<li>
MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS

</li>
</ul>The MM_ALLOCATE_PREFER_CONTIGUOUS and MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS flag bits are mutually exclusive. For more information about these flags, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556396">MM_ALLOCATE_XXX</a>.


## Return Value

<b>MmAllocateNodePagesForMdlEx</b> returns a pointer to an MDL structure if it is successful. Otherwise, if the routine fails to allocate any memory, the routine returns <b>NULL</b>.

A return value of <b>NULL</b> indicates that no physical memory pages are available in the specified address ranges, or that there is not enough memory pool available to allocate the MDL structure.

If the routine successfully allocates some, but not all, of the requested memory, the MDL describes as much physical memory as the routine was able to allocate.

## Remarks

In a non-uniform memory access (NUMA) multiprocessor system, the caller can specify an ideal node from which to allocate the memory. A node is a collection of processors that share fast access to a region of memory. In a non-NUMA multiprocessor or a single-processor system, <b>MmAllocateNodePagesForMdlEx</b> treats all memory as belonging to a single node and allocates memory from this node.

By default, the physical memory pages that <b>MmAllocateNodePagesForMdlEx</b> returns are not contiguous pages. Callers can override the default behavior of this routine by setting the MM_ALLOCATE_PREFER_CONTIGUOUS or MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS flag bit in the <i>Flags</i> parameter.

<b>MmAllocateNodePagesForMdlEx</b> does not map the allocated physical memory into virtual memory. If necessary, the caller can call a routine such as <a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a> to map the physical memory pages described by the MDL.

<b>MmAllocateNodePagesForMdlEx</b> is designed for kernel-mode drivers that do not need corresponding virtual addresses (that is, they need physical pages and do not need them to be physically contiguous), and for kernel-mode drivers that can achieve substantial performance gains if physical memory for a device is allocated in a specific physical address range (for example, an AGP graphics card).

Depending on how much physical memory is currently available in the requested ranges, <b>MmAllocateNodePagesForMdlEx</b> might return an MDL that describes less memory than was requested. The routine also might return <b>NULL</b> if no memory was allocated. The caller should check the amount of memory that is actually allocated, as described by the MDL.

The caller must use <a href="..\wdm\nf-wdm-mmfreepagesfrommdl.md">MmFreePagesFromMdl</a> to release the memory pages that are described by an MDL that was created by <b>MmAllocateNodePagesForMdlEx</b>. After calling <b>MmFreePagesFromMdl</b>, the caller must also call <a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a> to release the memory allocated for the MDL structure.

By default, <b>MmAllocateNodePagesForMdlEx</b> fills the pages that it allocates with zeros. The caller can specify the MM_DONT_ZERO_ALLOCATION flag to override this default and to possibly improve performance.
<div class="alert"><b>Note</b>    Memory that <b>MmAllocateNodePagesForMdlEx</b> allocates is uninitialized if you specify the MM_DONT_ZERO_ALLOCATION flag. A kernel-mode driver must first zero this memory if the driver is going to make the memory visible to user-mode software (to avoid leaking potentially privileged contents). For more information about this flag, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556396">MM_ALLOCATE_XXX</a>.</div><div> </div>The maximum amount of memory that <b>MmAllocateNodePagesForMdlEx</b> can allocate in a single call is (4 gigabytes - PAGE_SIZE). The routine can satisfy an allocation request for this amount only if enough pages are available.

<b>MmAllocateNodePagesForMdlEx</b> runs at IRQL &lt;= APC_LEVEL. If necessary, your driver can call <b>MmAllocateNodePagesForMdlEx</b> at DISPATCH_LEVEL. However, you can improve driver performance by calling at APC_LEVEL or below.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL (See Remarks section.)" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556396">MM_ALLOCATE_XXX</a>

<a href="..\wdm\nf-wdm-kequeryhighestnodenumber.md">KeQueryHighestNodeNumber</a>

<a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>

<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>

<a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a>

<a href="..\wdm\nf-wdm-mmfreepagesfrommdl.md">MmFreePagesFromMdl</a>

<a href="..\wdm\ne-wdm-_memory_caching_type.md">MEMORY_CACHING_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmAllocateNodePagesForMdlEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>