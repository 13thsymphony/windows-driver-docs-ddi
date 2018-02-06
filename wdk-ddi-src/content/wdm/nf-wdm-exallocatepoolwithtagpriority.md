---
UID: NF:wdm.ExAllocatePoolWithTagPriority
title: ExAllocatePoolWithTagPriority function
author: windows-driver-content
description: The ExAllocatePoolWithTagPriority routine allocates pool memory of the specified type.
old-location: kernel\exallocatepoolwithtagpriority.htm
old-project: kernel
ms.assetid: 33087a37-e6fc-4b21-aa9e-e4617eeccd29
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.exallocatepoolwithtagpriority, k102_cca6adc7-0f37-4565-858d-a191062f4fbd.xml, wdm/ExAllocatePoolWithTagPriority, ExAllocatePoolWithTagPriority routine [Kernel-Mode Driver Architecture], ExAllocatePoolWithTagPriority
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExAllocatePool, IrqlExFree2, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExAllocatePoolWithTagPriority
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExAllocatePoolWithTagPriority function
The <b>ExAllocatePoolWithTagPriority</b> routine allocates pool memory of the specified type.

## Syntax

````
PVOID ExAllocatePoolWithTagPriority(
  _In_ POOL_TYPE        PoolType,
  _In_ SIZE_T           NumberOfBytes,
  _In_ ULONG            Tag,
  _In_ EX_POOL_PRIORITY Priority
);
````

## Parameters

`PoolType`

The type of pool memory to allocate. For a description of the available pool memory types, see <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>.

You can modify the <i>PoolType</i> value by bitwise-ORing this value with the POOL_RAISE_IF_ALLOCATION_FAILURE flag. This flag causes an exception to be raised if the request cannot be satisfied.

Similarly, you can modify the <i>PoolType</i> value by bitwise-ORing this value with the POOL_COLD_ALLOCATION flag as a hint to the kernel to allocate the memory from pages that are likely to be paged out  quickly. To reduce the amount of resident pool memory as much as possible, you should not reference these allocations frequently. The POOL_COLD_ALLOCATION flag is only advisory and is available starting with Windows XP.

`NumberOfBytes`

The number of bytes to allocate.

`Tag`

The pool tag to use for the allocated memory. For more information, see the <i>Tag</i> parameter of <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>.

`Priority`

The priority of this request. Set this parameter to one of the following <b>EX_POOL_PRIORITY</b> enumeration values.
<table>
<tr>
<th>Priority value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>LowPoolPriority</b>

</td>
<td>
Specifies that the system may fail the request when it runs low on resources. Driver allocations that can recover from an allocation failure use this priority.

</td>
</tr>
<tr>
<td>
<b>NormalPoolPriority</b>

</td>
<td>
Specifies that the system may fail the request when it runs very low on resources. Most drivers should use this value.

</td>
</tr>
<tr>
<td>
<b>HighPoolPriority</b>

</td>
<td>
Specifies that the system must not fail the request, unless it is completely out of resources. Drivers only use this value when it is critically important for the request to succeed.

</td>
</tr>
</table> 

The <b>EX_POOL_PRIORITY</b> enumeration defines <b><i>Xxx</i>SpecialPoolOverrun</b> and <b><i>Xxx</i>SpecialPoolUnderrun</b> variants to specify how memory should be allocated when <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> (or special pool) is enabled. If the driver specifies <b><i>Xxx</i>SpecialPoolUnderrun</b>, when the <a href="https://msdn.microsoft.com/ab464d5b-7bad-494e-80cd-e32ca9e9fa8d">memory manager</a> allocates memory from <a href="https://msdn.microsoft.com/b1381a75-279a-42b7-b18d-43aba796424b">special pool</a>, it allocates it at the start of a physical page. If the driver specifies <b><i>Xxx</i>SpecialPoolOverrun</b>, the memory manager allocates it at the end of a physical page.


## Return Value

<b>ExAllocatePoolWithTagPriority</b> returns <b>NULL</b> if there is insufficient memory in the free pool to satisfy the request unless POOL_RAISE_IF_ALLOCATION_FAILURE is specified. Otherwise, the routine returns a pointer to the allocated memory.

## Remarks

Callers of <b>ExAllocatePoolWithTagPriority</b> must be executing at IRQL &lt;= DISPATCH_LEVEL. A caller executing at DISPATCH_LEVEL must specify a <b>NonPaged</b><i>Xxx</i> value for <i>PoolType</i>. A caller executing at IRQL &lt;= APC_LEVEL can specify any <b>POOL_TYPE</b> value, but the IRQL and environment must also be considered for determining the page type.

If <i>NumberOfBytes</i> is PAGE_SIZE or greater, a page-aligned buffer is allocated. Memory allocations of PAGE_SIZE or less are allocated within a page and do not cross page boundaries. Memory allocations of less than PAGE_SIZE are not necessarily page-aligned but are aligned to 8-byte boundaries in 32-bit systems and to 16-byte boundaries in 64-bit systems.
<div class="alert"><b>Note</b>  Do not set <i>NumberOfBytes</i> = 0. Avoid zero-length allocations because they waste pool header space and, in many cases, indicate a potential validation issue in the calling code. For this reason, <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> flags such allocations as possible errors.</div><div> </div>The system automatically sets certain standard event objects when the amount of pool (paged or nonpaged) is high or low. Drivers can wait for these events to tune their pool usage. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563847">Standard Event Objects</a>.

In a non-uniform memory access (NUMA) multiprocessor architecture, <b>ExAllocatePoolWithTagPriority</b> tries to allocate memory that is local to the processor that is calling <b>ExAllocatePoolWithTagPriority</b>. If no local memory is available, <b>ExAllocatePoolWithTagPriority</b> allocates the closest available memory.
<div class="alert"><b>Note</b>  Memory that <b>ExAllocatePoolWithTagPriority</b> allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL (see Remarks section)" |
| **DDI compliance rules** | IrqlExAllocatePool, IrqlExFree2, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo |

## See Also

<a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>

<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>

<a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAllocatePoolWithTagPriority routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>