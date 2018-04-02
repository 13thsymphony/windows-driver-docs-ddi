---
UID: NF:wdm.ExInterlockedInsertTailList
title: ExInterlockedInsertTailList function
author: windows-driver-content
description: The ExInterlockedInsertTailList routine atomically inserts an entry at the end of a doubly linked list of LIST_ENTRY structures.
old-location: kernel\exinterlockedinserttaillist.htm
old-project: kernel
ms.assetid: cd322d64-4005-426c-b3ce-0fe8f6ce868e
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExInterlockedInsertTailList, ExInterlockedInsertTailList routine [Kernel-Mode Driver Architecture], k102_a6d47e7b-63d2-48e9-9f6a-99f733194c1b.xml, kernel.exinterlockedinserttaillist, wdm/ExInterlockedInsertTailList
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
req.ddi-compliance: IoAllocateFree, IoReuseIrp, MarkingInterlockedQueuedIrps, RemoveLockCheck, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockRelease2, RemoveLockReleaseCleanup, RemoveLockReleaseClose, RemoveLockReleaseCreate, RemoveLockReleaseDeviceControl, RemoveLockReleaseInternalDeviceControl, RemoveLockReleasePower, RemoveLockReleaseRead, RemoveLockReleaseShutdown, RemoveLockReleaseSystemControl, RemoveLockReleaseWrite
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExInterlockedInsertTailList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExInterlockedInsertTailList function
The <b>ExInterlockedInsertTailList</b> routine atomically inserts an entry at the end of a doubly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structures.

## Syntax

```
NTKERNELAPI PLIST_ENTRY ExInterlockedInsertTailList(
  PLIST_ENTRY                                  ListHead,
  __drv_aliasesMem PLIST_ENTRY                 ListEntry,
  _Requires_lock_not_held_(*_Curr_)PKSPIN_LOCK Lock
);
```

## Parameters

`ListHead`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that serves as the list header.

`ListEntry`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that represents the entry to be inserted into the list.

`Lock`

A pointer to a <b>KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>. You must use this spin lock only with the <b>ExInterlocked<i>Xxx</i>List</b> routines.


## Return Value

<b>ExInterlockedInsertTailList</b> returns a pointer to the last entry of the list <u>before</u> the new entry was inserted. If the list was empty, the routine returns <b>NULL</b>.

## Remarks

<b>ExInterlockedInsertTailList</b> performs the same operation as <a href="https://msdn.microsoft.com/library/windows/hardware/ff547823">InsertTailList</a>, but atomically. Do not mix atomic and non-atomic calls on the same list.

For more information about using this routine to implement a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

The <b>ExInterlockedInsertTailList</b> routine can be called at any IRQL. The storage for the <i>ListHead</i> parameter and the list entries must be resident at all IRQLs.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level (see Remarks section) |
| **DDI compliance rules** | IoAllocateFree, IoReuseIrp, MarkingInterlockedQueuedIrps, RemoveLockCheck, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockRelease2, RemoveLockReleaseCleanup, RemoveLockReleaseClose, RemoveLockReleaseCreate, RemoveLockReleaseDeviceControl, RemoveLockReleaseInternalDeviceControl, RemoveLockReleasePower, RemoveLockReleaseRead, RemoveLockReleaseShutdown, RemoveLockReleaseSystemControl, RemoveLockReleaseWrite |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545397">ExInterlockedInsertHeadList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547799">InitializeListHead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547823">InsertTailList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>