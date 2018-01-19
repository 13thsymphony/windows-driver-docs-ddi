---
UID : NF:wdm.ExQueueWorkItem
title : ExQueueWorkItem function
author : windows-driver-content
description : ExQueueWorkItem inserts a given work item into a queue from which a system worker thread removes the item and gives control to the routine that the caller supplied to ExInitializeWorkItem.
old-location : ifsk\exqueueworkitem.htm
old-project : ifsk
ms.assetid : 287affe1-c5d4-4b36-8017-d1fef6088cf8
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ExQueueWorkItem
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntifs.h, Fltkernel.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ExQueueWorkItem
req.alt-loc : NtosKrnl.exe
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
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# ExQueueWorkItem function
<b>ExQueueWorkItem</b> inserts a given work item into a queue from which a system worker thread removes the item and gives control to the routine that the caller supplied to <a href="..\wdm\nf-wdm-exinitializeworkitem.md">ExInitializeWorkItem</a>.

## Syntax

````
VOID ExQueueWorkItem(
  _Inout_ PWORK_QUEUE_ITEM WorkItem,
  _In_    WORK_QUEUE_TYPE  QueueType
);
````

## Parameters

`WorkItem`

Pointer to the work item. This work item must have been initialized by a preceding call to <a href="..\wdm\nf-wdm-exinitializeworkitem.md">ExInitializeWorkItem</a>.

`QueueType`

Specifies the queue into which the work item pointed to by <i>WorkItem</i> is to be inserted. <i>QueueType</i> can be either of the following: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>CriticalWorkQueue</b>

</td>
<td>
Insert the <i>WorkItem</i> into the queue from which a system thread with a real-time priority attribute will process the work item. 

</td>
</tr>
<tr>
<td>
<b>DelayedWorkQueue</b>

</td>
<td>
Insert the <i>WorkItem</i> into the queue from which a system thread with a variable priority attribute will process the work item. 

</td>
</tr>
</table>
 

The <i>QueueType</i> value <b>HyperCriticalWorkQueue</b> is reserved for system use.


## Return Value

None

## Remarks

The callback routine that was specified in the <i>Routine</i> parameter to <a href="..\wdm\nf-wdm-exinitializeworkitem.md">ExInitializeWorkItem</a> is called in a system context at IRQL PASSIVE_LEVEL. This caller-supplied routine is responsible for freeing the work item when it is no longer needed by calling <a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a> or <a href="..\wdm\nf-wdm-exfreepoolwithtag.md">ExFreePoolWithTag</a>.

System worker threads are a limited resource. Drivers must not permanently reserve a work item for the driver's use. Work items are designed for operations that complete quickly. Drivers should free any work items that they allocate as soon as possible.

A driver must not wait for its callback routine to complete an operation if it is already holding one synchronization object and might attempt to acquire another. To prevent deadlock, a driver should release any currently held semaphores, mutexes, resource variables, and so forth before it calls <b>ExQueueWorkItem</b>. 

The value of <i>QueueType</i> determines the runtime priority at which the callback routine is run, as follows: 

If the callback runs in the system thread with a real-time priority attribute, the callback routine cannot be preempted except by threads with higher real-time priorities. 

If the callback runs in the system thread with a variable priority attribute, the callback can be preempted by threads with higher variable and real-time priorities, and the callback is scheduled to run round-robin with other threads of the same priority for a quantum each. 

Threads at either priority remain interruptible.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntifs.h, Fltkernel.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exfreepoolwithtag.md">ExFreePoolWithTag</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exinitializeworkitem.md">ExInitializeWorkItem</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioallocateworkitem.md">IoAllocateWorkItem</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iofreeworkitem.md">IoFreeWorkItem</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_work_queue_item.md">WORK_QUEUE_ITEM</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20ExQueueWorkItem routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>