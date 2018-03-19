---
UID: NF:wdm.IoQueueWorkItemEx
title: IoQueueWorkItemEx function
author: windows-driver-content
description: The IoQueueWorkItemEx routine associates a WorkItemEx routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread.
old-location: kernel\ioqueueworkitemex.htm
old-project: kernel
ms.assetid: 277a6e13-dc2d-4170-a141-9df5b93eb504
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoQueueWorkItemEx, IoQueueWorkItemEx routine [Kernel-Mode Driver Architecture], k104_e14fae9d-5b8c-4683-8226-8694de253b64.xml, kernel.ioqueueworkitemex, wdm/IoQueueWorkItemEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoQueueWorkItemEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoQueueWorkItemEx function
The <b>IoQueueWorkItemEx</b> routine associates a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566381">WorkItemEx</a> routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread.

## Syntax

````
VOID IoQueueWorkItemEx(
  _In_     PIO_WORKITEM            IoWorkItem,
  _In_     PIO_WORKITEM_ROUTINE_EX WorkerRoutine,
  _In_     WORK_QUEUE_TYPE         QueueType,
  _In_opt_ PVOID                   Context
);
````

## Parameters

`IoWorkItem`

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a> structure that was allocated by <a href="..\wdm\nf-wdm-ioallocateworkitem.md">IoAllocateWorkItem</a> or initialized by <a href="..\wdm\nf-wdm-ioinitializeworkitem.md">IoInitializeWorkItem</a>.

`WorkerRoutine`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566381">WorkItemEx</a> routine.

`QueueType`

Specifies a <a href="..\wdm\ne-wdm-_work_queue_type.md">WORK_QUEUE_TYPE</a> value that stipulates the type of system worker thread to handle the work item. Drivers must specify <b>DelayedWorkQueue</b>.

`Context`

Specifies driver-specific information for the work item. The system passes this value as the <i>Context</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566381">WorkItemEx</a>.


## Return Value

None

## Remarks

For more information about work items, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566381">WorkItemEx</a>



<a href="..\wdm\nf-wdm-ioallocateworkitem.md">IoAllocateWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a>



<a href="..\wdm\nf-wdm-ioinitializeworkitem.md">IoInitializeWorkItem</a>



<a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a>