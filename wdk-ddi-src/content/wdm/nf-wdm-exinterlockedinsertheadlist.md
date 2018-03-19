---
UID: NF:wdm.ExInterlockedInsertHeadList
title: ExInterlockedInsertHeadList function
author: windows-driver-content
description: The ExInterlockedInsertHeadList routine atomically inserts an entry at the beginning of a doubly linked list of LIST_ENTRY structures.
old-location: kernel\exinterlockedinsertheadlist.htm
old-project: kernel
ms.assetid: 91640a96-abad-424e-b9bd-301dad2b6aac
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ExInterlockedInsertHeadList, ExInterlockedInsertHeadList routine [Kernel-Mode Driver Architecture], k102_35e48cb9-2d0b-42df-aee0-b391b0ade424.xml, kernel.exinterlockedinsertheadlist, wdm/ExInterlockedInsertHeadList
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
-	ExInterlockedInsertHeadList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExInterlockedInsertHeadList function
The <b>ExInterlockedInsertHeadList</b> routine atomically inserts an entry at the beginning of a doubly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structures.

## Syntax

````
PLIST_ENTRY ExInterlockedInsertHeadList(
  _Inout_ PLIST_ENTRY ListHead,
  _Inout_ PLIST_ENTRY ListEntry,
  _Inout_ PKSPIN_LOCK Lock
);
````

## Parameters

`ListHead`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that serves as the list header.

`ListEntry`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that represents the entry to be inserted into the list.

`Lock`

A pointer to a <b>KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>. You must use this spin lock only with the <b>ExInterlocked<i>Xxx</i>List</b> routines.


## Return Value

<b>ExInterlockedInsertHeadList</b> returns a pointer to the first entry of the list <u>before</u> the new entry was inserted. If the list was empty, the routine returns <b>NULL</b>.

## Remarks

<b>ExInterlockedInsertHeadList</b> performs the same operation as <a href="..\wudfwdm\nf-wudfwdm-insertheadlist.md">InsertHeadList</a>, but atomically. Do not mix atomic and non-atomic calls on the same list.

For more information about using this routine to implement a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

The <b>ExInterlockedInsertHeadList</b> routine can be called at any IRQL. The storage for the <i>ListHead</i> parameter and the list entries must be resident at all IRQLs.

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

<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>



<a href="..\wudfwdm\nf-wudfwdm-insertheadlist.md">InsertHeadList</a>



<a href="..\wudfwdm\nf-wudfwdm-initializelisthead.md">InitializeListHead</a>



<a href="..\wdm\nf-wdm-exinterlockedinserttaillist.md">ExInterlockedInsertTailList</a>



<a href="..\wdm\nf-wdm-exinterlockedremoveheadlist.md">ExInterlockedRemoveHeadList</a>