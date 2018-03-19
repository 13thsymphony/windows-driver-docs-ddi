---
UID: NF:wdm.KeInsertByKeyDeviceQueue
title: KeInsertByKeyDeviceQueue function
author: windows-driver-content
description: The KeInsertByKeyDeviceQueue routine acquires the spin lock for the specified DeviceQueue and queues an entry according to the specified sort-key value if the device queue is set to a busy state.
old-location: kernel\keinsertbykeydevicequeue.htm
old-project: kernel
ms.assetid: fa395673-108f-4cf0-b05f-a160aa0b02ea
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeInsertByKeyDeviceQueue, KeInsertByKeyDeviceQueue routine [Kernel-Mode Driver Architecture], k105_14a9196c-2ce0-4384-9e72-b957523f49b6.xml, kernel.keinsertbykeydevicequeue, wdm/KeInsertByKeyDeviceQueue
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
-	KeInsertByKeyDeviceQueue
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeInsertByKeyDeviceQueue function
The <b>KeInsertByKeyDeviceQueue</b> routine acquires the spin lock for the specified <i>DeviceQueue</i> and queues an entry according to the specified sort-key value if the device queue is set to a busy state.

## Syntax

````
BOOLEAN KeInsertByKeyDeviceQueue(
  _Inout_ PKDEVICE_QUEUE       DeviceQueue,
  _Inout_ PKDEVICE_QUEUE_ENTRY DeviceQueueEntry,
  _In_    ULONG                SortKey
);
````

## Parameters

`DeviceQueue`

Pointer to a control object of the device queue type for which the caller provides the storage.

`DeviceQueueEntry`

Pointer to the device queue entry to be inserted into the device queue according to the specific key value.

`SortKey`

Specifies the sort-key value that determines the position in the device queue in which to insert the entry.


## Return Value

If the device queue is empty, <b>FALSE</b> is returned, meaning the <i>DeviceQueueEntry</i> is not inserted in the device queue.

## Remarks

The specified device queue spin lock is acquired and the state of the device queue is checked. If the device queue is set to a busy state, the IRP specified by the <i>DeviceQueueEntry</i> is inserted into the device queue according to its sort key value and the device queue spin lock is released.

The new entry is positioned in the device queue after any entries in the queue with sort key values less than or equal to its sort key value and preceding any entries with sort key values that are greater.

If <b>KeInsertByKeyDeviceQueue</b> returns <b>FALSE</b>, the caller must begin processing the IRP. A call to <a href="..\wdm\nf-wdm-keinsertdevicequeue.md">KeInsertDeviceQueue</a> or <b>KeInsertByKeyDeviceQueue</b> when the queue is empty causes the device queue to transition from a not-busy state to a busy state.

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

<a href="..\wdm\nf-wdm-keinsertdevicequeue.md">KeInsertDeviceQueue</a>



<a href="..\wdm\nf-wdm-keremovedevicequeue.md">KeRemoveDeviceQueue</a>



<a href="..\wdm\nf-wdm-keinitializedevicequeue.md">KeInitializeDeviceQueue</a>



<a href="..\wdm\nf-wdm-keremoveentrydevicequeue.md">KeRemoveEntryDeviceQueue</a>