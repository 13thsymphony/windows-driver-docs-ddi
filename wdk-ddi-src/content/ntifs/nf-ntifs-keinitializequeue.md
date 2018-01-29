---
UID : NF:ntifs.KeInitializeQueue
title : KeInitializeQueue function
author : windows-driver-content
description : The KeInitializeQueue routine initializes a queue object on which threads can wait for entries.
old-location : ifsk\keinitializequeue.htm
old-project : ifsk
ms.assetid : 8dd47333-679a-482b-bd45-1e73505b3fea
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KeInitializeQueue, ifsk.keinitializequeue, KeInitializeQueue routine [Installable File System Drivers], ntifs/KeInitializeQueue, keref_85ea0829-c42c-4411-8ad9-a32d8eb0a40f.xml
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
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# KeInitializeQueue function
The <b>KeInitializeQueue</b> routine initializes a queue object on which threads can wait for entries.

## Syntax

````
VOID KeInitializeQueue(
  _Out_ PRKQUEUE Queue,
  _In_  ULONG    Count
);
````

## Parameters

`Queue`

Pointer to a KQUEUE structure for which the caller must provide resident storage in nonpaged pool. This structure is defined as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _KQUEUE {
    DISPATCHER_HEADER Header;
    LIST_ENTRY EntryListHead;
    ULONG CurrentCount;
    ULONG MaximumCount;
    LIST_ENTRY ThreadListHead;
} KQUEUE, *PKQUEUE, *RESTRICTED_POINTER PRKQUEUE;</pre>
</td>
</tr>
</table></span></div><table>
<tr>
<th>Member</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>Header</b>

</td>
<td>
Queue header.

</td>
</tr>
<tr>
<td>
<b>EntryListHead</b>

</td>
<td>
Pointer to the first entry in the queue.

</td>
</tr>
<tr>
<td>
<b>CurrentCount</b>

</td>
<td>
Current number of threads waiting on the queue.

</td>
</tr>
<tr>
<td>
<b>MaximumCount</b>

</td>
<td>
Maximum number of concurrent threads the queue can satisfy waits for.

</td>
</tr>
<tr>
<td>
<b>ThreadListHead</b>

</td>
<td>
Pointer to the first entry in the thread list.

</td>
</tr>
</table>

`Count`

The maximum number of threads for which the waits on the queue object can be satisfied concurrently. If this parameter is not supplied, the number of processors in the machine is used.


## Return Value

None

## Remarks

Usually the caller of <b>KeInitializeQueue</b> also creates a set of dedicated threads to queue and dequeue its entries. Such a caller can specify an explicit <i>Count</i> to prevent too many of its dedicated threads from waiting concurrently on its queue object. 

<b>KeInitializeQueue</b> sets the queue object's initial signal state to Not Signaled.

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

<a href="..\ntifs\nf-ntifs-keinsertqueue.md">KeInsertQueue</a>

<a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a>

<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>

<a href="..\wdm\nf-wdm-pscreatesystemthread.md">PsCreateSystemThread</a>

<a href="..\ntifs\nf-ntifs-keremovequeue.md">KeRemoveQueue</a>

<a href="..\ntifs\nf-ntifs-kerundownqueue.md">KeRundownQueue</a>

<a href="..\wdm\nf-wdm-ioallocateworkitem.md">IoAllocateWorkItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20KeInitializeQueue routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>