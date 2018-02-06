---
UID: NF:wdm.KeRemoveEntryDeviceQueue
title: KeRemoveEntryDeviceQueue function
author: windows-driver-content
description: The KeRemoveEntryDeviceQueue routine returns whether the specified entry is in the device queue and removes it, if it was queued, from the device queue.
old-location: kernel\keremoveentrydevicequeue.htm
old-project: kernel
ms.assetid: 2dc32517-3730-4a1c-a59a-f5036d6f54ef
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.keremoveentrydevicequeue, KeRemoveEntryDeviceQueue, KeRemoveEntryDeviceQueue routine [Kernel-Mode Driver Architecture], k105_351b5540-c341-46d1-b2da-1ea88f78b7b2.xml, wdm/KeRemoveEntryDeviceQueue
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
req.ddi-compliance: IrqlKeDispatchLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeRemoveEntryDeviceQueue
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeRemoveEntryDeviceQueue function
The <b>KeRemoveEntryDeviceQueue</b> routine returns whether the specified entry is in the device queue and removes it, if it was queued, from the device queue.

## Syntax

````
BOOLEAN KeRemoveEntryDeviceQueue(
  _Inout_ PKDEVICE_QUEUE       DeviceQueue,
  _Inout_ PKDEVICE_QUEUE_ENTRY DeviceQueueEntry
);
````

## Parameters

`DeviceQueue`

Pointer to an initialized device queue object for which the caller provides the storage.

`DeviceQueueEntry`

Pointer to the entry to be removed from the specified <i>DeviceQueue</i>.


## Return Value

If the <i>DeviceQueueEntry</i> is queued, it is removed and <b>KeRemoveEntryDeviceQueue</b> returns <b>TRUE</b>.

## Remarks

The IRQL is set to DISPATCH_LEVEL and the <i>DeviceQueue</i> spin lock is acquired.

If the specified <i>DeviceQueueEntry</i> is not in the queue, the IRP either is already being processed, or the IRP has been canceled. In this case, <b>KeRemoveEntryDeviceQueue</b> simply returns <b>FALSE</b>.

The specified <i>DeviceQueue</i> spin lock is released and IRQL is restored to its previous value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | IrqlKeDispatchLte, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-keinsertdevicequeue.md">KeInsertDeviceQueue</a>

<a href="..\wdm\nf-wdm-keremovedevicequeue.md">KeRemoveDeviceQueue</a>

<a href="..\wdm\nf-wdm-keinitializedevicequeue.md">KeInitializeDeviceQueue</a>

<a href="..\wdm\nf-wdm-keremovebykeydevicequeue.md">KeRemoveByKeyDeviceQueue</a>

<a href="..\wdm\nf-wdm-keinsertbykeydevicequeue.md">KeInsertByKeyDeviceQueue</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeRemoveEntryDeviceQueue routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>