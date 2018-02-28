---
UID: NF:wdm.ExInitializeNPagedLookasideList
title: ExInitializeNPagedLookasideList function
author: windows-driver-content
description: The ExInitializeNPagedLookasideList routine initializes a lookaside list for nonpaged entries of the specified size.
old-location: kernel\exinitializenpagedlookasidelist.htm
old-project: kernel
ms.assetid: d783feff-d187-4a2f-8d3d-b5221b03459a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ExInitializeNPagedLookasideList, ExInitializeNPagedLookasideList routine [Kernel-Mode Driver Architecture], k102_054ed856-4da7-42e9-a413-baefdd1064ed.xml, kernel.exinitializenpagedlookasidelist, wdm/ExInitializeNPagedLookasideList
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExInitializeNPagedLookasideList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExInitializeNPagedLookasideList function
The <b>ExInitializeNPagedLookasideList</b> routine initializes a lookaside list for nonpaged entries of the specified size.

## Syntax

````
VOID ExInitializeNPagedLookasideList(
  _Out_    PNPAGED_LOOKASIDE_LIST Lookaside,
  _In_opt_ PALLOCATE_FUNCTION     Allocate,
  _In_opt_ PFREE_FUNCTION         Free,
  _In_     ULONG                  Flags,
  _In_     SIZE_T                 Size,
  _In_     ULONG                  Tag,
  _In_     USHORT                 Depth
);
````

## Parameters

`Lookaside`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a> structure to initialize. The caller must use nonpaged system space for the structure. On 64-bit platforms, this structure must be 16-byte aligned.

`Allocate`

A pointer to either a caller-supplied function for allocating an entry when the lookaside list is empty, or to <b>NULL</b>. If non-<b>NULL</b>, the pointer is to a function with the prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PVOID XxxAllocate(
  __in POOL_TYPE  PoolType,           // NonPagedPool 
  __in SIZE_T  NumberOfBytes,         // value of Size
  __in ULONG  Tag                     // value of Tag
);</pre>
</td>
</tr>
</table></span></div>
If the <i>Allocate</i> parameter is <b>NULL</b>, subsequent calls to <a href="..\wdm\nf-wdm-exallocatefromnpagedlookasidelist.md">ExAllocateFromNPagedLookasideList</a> automatically allocate entries whenever the lookaside list is empty.

`Free`

A pointer to either a caller-supplied function for freeing an entry whenever the lookaside list is full, or to <b>NULL</b>. If non-<b>NULL</b>, the pointer is to a function with the prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID XxxFree(
  __in PVOID  Buffer
);</pre>
</td>
</tr>
</table></span></div>
If the <i>Free</i> parameter is <b>NULL</b>, subsequent calls to <a href="..\wdm\nf-wdm-exfreetonpagedlookasidelist.md">ExFreeToNPagedLookasideList</a> automatically release the given entry back to nonpaged pool whenever the list is full, that is, currently holding the system-determined maximum number of entries.

`Flags`

Starting in Windows 8, this parameter specifies an optional flag value to modify the default behavior of the <b>ExInitializeNPagedLookasideList</b> routine. Compatible flag bits include the following.

<table>
<tr>
<th>Flag bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
POOL_NX_ALLOCATION

</td>
<td>
Allocate non-executable memory.

</td>
</tr>
<tr>
<td>
POOL_RAISE_IF_ALLOCATION_FAILURE

</td>
<td>
If the allocation fails, raise an exception.

</td>
</tr>
</table>
 

Before Windows 8, this parameter is not used and must be zero.

`Size`

Specifies the size, in bytes, for each nonpaged entry to be allocated subsequently. This parameter must not be less than the required minimum size, LOOKASIDE_MINIMUM_BLOCK_SIZE, which is defined in the Wdm.h header file.

`Tag`

Specifies the pool tag to use when allocating lookaside list entries. For more information about pool tags, see the <i>Tag</i> parameter of <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>.

`Depth`

Reserved. Must be zero.


## Return Value

None

## Remarks

After calling <b>ExInitializeNPagedLookasideList</b>, memory blocks of the caller-specified <i>Size</i> can be allocated from and freed to the lookaside list with calls to <a href="..\wdm\nf-wdm-exallocatefromnpagedlookasidelist.md">ExAllocateFromNPagedLookasideList</a> and <a href="..\wdm\nf-wdm-exfreetonpagedlookasidelist.md">ExFreeToNPagedLookasideList</a>, respectively. Such dynamically allocated and freed entries can be any data structure or fixed-size buffer that the caller uses while the system is running, particularly if the caller cannot predetermine how many such entries will be in use at any given moment. The layout and contents of each fixed-size entry are caller-determined. 

<b>ExInitializeNPagedLookasideList</b> initializes the system state to track usage of the given lookaside list, as follows:

<ul>
<li>
Zero-initializes the counters to be maintained for entries.

</li>
<li>
Stores the entry points of the caller-supplied <b><i>Xxx</i>Allocate</b> and <b><i>Xxx</i>Free</b> routines, if any, or sets these entry points to <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> and <a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>, respectively.

</li>
<li>
Initializes a system spin lock to control allocations from and frees to the lookaside list in a multiprocessor-safe manner if necessary.

</li>
<li>
Stores the caller-supplied entry <i>Size</i> and list <i>Tag</i>.

</li>
<li>
Sets up the system-determined limits (minimum and maximum) on the number of entries to be held in the lookaside list, which can be adjusted subsequently if system-wide demand for entries is higher or lower than anticipated.

</li>
<li>
Sets up the system-determined flags, which control the type of memory from which entries will be allocated subsequently.

</li>
</ul>
The system maintains a set of all lookaside lists currently in use. As demand for lookaside list entries and on available nonpaged memory varies while the system runs, the system adjusts its limits for the number of entries to be held in each nonpaged lookaside list dynamically.

Drivers must always use explicitly free any lookaside lists they create before unloading. To do otherwise is a serious programming error. Use <a href="..\wdm\nf-wdm-exdeletenpagedlookasidelist.md">ExDeleteNPagedLookasideList</a> to free the list.

<b>ExInitializeNPagedLookasideList</b> sets up the opaque list head at the caller-supplied location but preallocates no memory for list entries. Subsequently, the initial entries are allocated dynamically as calls to <b>ExAllocateFromNPagedLookasideList</b> occur, and these initial entries are held in the lookaside list as reciprocal calls to <b>ExFreeToNPagedLookasideList</b> occur. Entries collect in the given lookaside list until the system-determined maximum is reached, whereupon any additional entries are returned to nonpaged pool as they are freed. If the list becomes empty, allocate requests are satisfied by the <b><i>Xxx</i>Allocate</b> function specified at list initialization or by <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>.

It is more efficient to pass <b>NULL</b> pointers for the <i>Allocate</i> and <i>Free</i> parameters of <b>ExInitializeNPagedLookasideList</b> whenever the user of a lookaside list does nothing more than allocate and release fixed-size entries. However, any component that uses a lookaside list might supply these functions to do additional caller-determined processing, such as tracking its own dynamic memory usage by maintaining state about the number of entries it allocates and frees.

If the caller of <b>ExInitializeNPagedLookasideList</b> supplies an <b><i>Xxx</i>Allocate</b> function, that routine must allocate entries for the lookaside list using the given input parameters when it calls <b>ExAllocatePoolWithTag.</b>

Starting with Windows Vista, a similar routine, <a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a>, initializes a lookaside list that is described by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a> structure. Unlike the <b><i>Xxx</i>Allocate</b> and <b><i>Xxx</i>Free</b> routines for a lookaside list that uses an <b>NPAGED_LOOKASIDE_LIST</b> structure, the allocation and deallocation routines for a lookaside list that uses the <b>LOOKASIDE_LIST_EX</b> structure receive a context pointer as an input parameter. These routines can use this context to store private data for the lookaside list. If your driver is intended to run only in Windows Vista and later versions of Windows, consider using <b>ExInitializeLookasideListEx</b> instead of <b>ExInitializeNPagedLookasideList</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.

Callers of <b>ExInitializeNPagedLookasideList</b> can be running at IRQL &lt;= DISPATCH_LEVEL, but are typically running at IRQL = PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL (see Remarks section)" |

## See Also

<a href="..\wdm\nf-wdm-exfreetonpagedlookasidelist.md">ExFreeToNPagedLookasideList</a>



<a href="..\wdm\nf-wdm-exallocatefromnpagedlookasidelist.md">ExAllocateFromNPagedLookasideList</a>



<a href="..\wdm\nf-wdm-exinitializepagedlookasidelist.md">ExInitializePagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a>



<a href="..\wdm\nf-wdm-exdeletenpagedlookasidelist.md">ExDeleteNPagedLookasideList</a>



<a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>



<a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a>



<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInitializeNPagedLookasideList routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>