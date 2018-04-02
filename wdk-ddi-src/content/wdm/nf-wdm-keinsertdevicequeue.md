---
UID: NF:wdm.KeInsertDeviceQueue
title: KeInsertDeviceQueue function
author: windows-driver-content
description: The KeInsertDeviceQueue routine acquires the spin lock for the specified device queue object and, if the device queue is set to a busy state, queues the specified entry.
old-location: kernel\keinsertdevicequeue.htm
old-project: kernel
ms.assetid: d0e634e0-f0b4-49a7-9df5-7af0842154f4
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeInsertDeviceQueue, KeInsertDeviceQueue routine [Kernel-Mode Driver Architecture], k105_a527fbb6-bb60-4051-9983-e960d9406abe.xml, kernel.keinsertdevicequeue, wdm/KeInsertDeviceQueue
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
req.ddi-compliance: IrqlDispatch, MarkingQueuedIrps, HwStorPortProhibitedDDIs, IrqlDispatch(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeInsertDeviceQueue
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeInsertDeviceQueue function
The <b>KeInsertDeviceQueue</b> routine acquires the spin lock for the specified device queue object and, if the device queue is set to a busy state, queues the specified entry.

## Syntax

```
NTKERNELAPI BOOLEAN KeInsertDeviceQueue(
  PKDEVICE_QUEUE       DeviceQueue,
  PKDEVICE_QUEUE_ENTRY DeviceQueueEntry
);
```

## Parameters

`DeviceQueue`

Pointer to a control object of type device queue for which the caller provides the storage.

`DeviceQueueEntry`

Pointer to the device queue entry that is to be inserted.


## Return Value

If the device queue is empty, <b>FALSE</b> is returned and the <i>DeviceQueueEntry</i> is not inserted in the device queue.

## Remarks

If the device queue is set to a busy state, the specified <i>DeviceQueueEntry</i> is inserted at the tail of the device queue and the device queue spin lock is released.

If <b>KeInsertDeviceQueue</b> returns <b>FALSE</b>, the entry was not queued and the caller must begin processing the IRP. A call to <b>KeInsertDeviceQueue</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff552178">KeInsertByKeyDeviceQueue</a> when the queue is empty causes the device queue to change from a not-busy state to a busy state.

This routine is for code that queues an I/O request to a device driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** | IrqlDispatch, MarkingQueuedIrps, HwStorPortProhibitedDDIs, IrqlDispatch(storport) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552126">KeInitializeDeviceQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552178">KeInsertByKeyDeviceQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553156">KeRemoveDeviceQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553163">KeRemoveEntryDeviceQueue</a>