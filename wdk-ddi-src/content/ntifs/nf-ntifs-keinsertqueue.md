---
UID : NF:ntifs.KeInsertQueue
title : KeInsertQueue function
author : windows-driver-content
description : The KeInsertQueue routine inserts an entry at the tail of the given queue if it cannot immediately use the entry to satisfy a thread wait.
old-location : ifsk\keinsertqueue.htm
old-project : ifsk
ms.assetid : 0aee6102-e9e3-41dc-a222-36bebb3d4294
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ntifs/KeInsertQueue, KeInsertQueue routine [Installable File System Drivers], keref_0e1ad47f-c38b-40e8-8629-8d970d5e1a72.xml, ifsk.keinsertqueue, KeInsertQueue
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : <= DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# KeInsertQueue function
The <b>KeInsertQueue</b> routine inserts an entry at the tail of the given queue if it cannot immediately use the entry to satisfy a thread wait.

## Syntax

````
LONG KeInsertQueue(
  _Inout_ PRKQUEUE    Queue,
  _Inout_ PLIST_ENTRY Entry
);
````

## Parameters

`Queue`

Pointer to an initialized queue object for which the caller provides resident storage in nonpaged pool.

`Entry`

Pointer to an entry to be queued. This pointer must be a resident system-space address.


## Return Value

<b>KeInsertQueue</b> returns the previous signal state of the given <i>Queue</i>. If it was set to zero (that is, not signaled) before <b>KeInsertQueue</b> was called, <b>KeInsertQueue</b> returns zero, meaning that no entries were queued. If it was nonzero (signaled), <b>KeInsertQueue</b> returns the number of entries that were queued before <b>KeInsertQueue</b> was called.

## Remarks

Entries to be queued by <b>KeInsertQueue</b> must be allocated from nonpaged pool. For example, memory for caller-defined entries can be allocated with <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>. If the caller allocates entries of a fixed size, creating a lookaside list with <a href="..\wdm\nf-wdm-exinitializenpagedlookasidelist.md">ExInitializeNPagedLookasideList</a> and allocating from it with <a href="..\wdm\nf-wdm-exallocatefromnpagedlookasidelist.md">ExAllocateFromNPagedLookasideList</a> is more efficient than making frequent calls to <b>ExAllocatePoolWithTag</b>, particularly for entries whose size is not a multiple of PAGE_SIZE. 

If any threads are waiting on the queue object when <b>KeInsertQueue</b> is called, a single thread's wait is satisfied by this call. The thread is dispatched for execution with the given <i>Entry</i> pointer. 

If no threads are currently waiting on the queue object when <b>KeInsertQueue</b> is called, the given entry is inserted in the queue, and the queue object's signal state is incremented. 

For more information about using driver-managed internal queues, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544165">Driver-Managed Queues</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-exallocatefromnpagedlookasidelist.md">ExAllocateFromNPagedLookasideList</a>

<a href="..\ntifs\nf-ntifs-keinsertheadqueue.md">KeInsertHeadQueue</a>

<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>

<a href="..\wdm\nf-wdm-exinitializenpagedlookasidelist.md">ExInitializeNPagedLookasideList</a>

<a href="..\ntifs\nf-ntifs-keremovequeue.md">KeRemoveQueue</a>

<a href="..\ntifs\nf-ntifs-keinitializequeue.md">KeInitializeQueue</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20KeInsertQueue routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>