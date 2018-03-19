---
UID: NF:wdm.IoAllocateWorkItem
title: IoAllocateWorkItem function
author: windows-driver-content
description: The IoAllocateWorkItem routine allocates a work item.
old-location: kernel\ioallocateworkitem.htm
old-project: kernel
ms.assetid: 950e31ff-2e8e-4dd3-9d6c-d3d86fd69472
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoAllocateWorkItem, IoAllocateWorkItem routine [Kernel-Mode Driver Architecture], k104_6cb480b8-6cf9-4c68-953e-8a1c8153087a.xml, kernel.ioallocateworkitem, wdm/IoAllocateWorkItem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating system, and in Windows Me. This routine is not available in Windows 98.
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
-	IoAllocateWorkItem
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoAllocateWorkItem function
The <b>IoAllocateWorkItem</b> routine allocates a work item.

## Syntax

````
PIO_WORKITEM IoAllocateWorkItem(
  _In_ PDEVICE_OBJECT DeviceObject
);
````

## Parameters

`DeviceObject`

Pointer to the caller's driver object or to one of the caller's device objects. If the caller will later pass the work item to <a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a>, <i>DeviceObject</i> must point to a device object.


## Return Value

<b>IoAllocateWorkItem</b> returns a pointer to the allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a> structure. The routine returns <b>NULL</b> if sufficient resources do not exist.

## Remarks

The driver must free the work item that is returned by <b>IoAllocateWorkItem</b> by calling <a href="..\wdm\nf-wdm-iofreeworkitem.md">IoFreeWorkItem</a>.

<b>IoAllocateWorkItem</b> both allocates and initializes a work item. A related routine, <a href="..\wdm\nf-wdm-ioinitializeworkitem.md">IoInitializeWorkItem</a>, initializes a work item in storage that the driver has previously allocated. Do not call <b>IoInitializeWorkItem</b> to initialize a work item that was allocated by <b>IoAllocateWorkItem</b>.

For more information about work items, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating system, and in Windows Me. This routine is not available in Windows 98.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a>



<a href="..\wdm\nf-wdm-iofreeworkitem.md">IoFreeWorkItem</a>



<a href="..\wdm\nf-wdm-ioqueueworkitemex.md">IoQueueWorkItemEx</a>



<a href="..\wdm\nf-wdm-ioinitializeworkitem.md">IoInitializeWorkItem</a>



<a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a>