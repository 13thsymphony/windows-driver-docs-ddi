---
UID: NF:wdm.ExInterlockedInsertTailList
title: ExInterlockedInsertTailList function
author: windows-driver-content
description: The ExInterlockedInsertTailList routine atomically inserts an entry at the end of a doubly linked list of LIST_ENTRY structures.
old-location: kernel\exinterlockedinserttaillist.htm
old-project: kernel
ms.assetid: cd322d64-4005-426c-b3ce-0fe8f6ce868e
ms.author: windowsdriverdev
ms.date: 2/24/2018
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

````
PLIST_ENTRY ExInterlockedInsertTailList(
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

<b>ExInterlockedInsertTailList</b> returns a pointer to the last entry of the list <u>before</u> the new entry was inserted. If the list was empty, the routine returns <b>NULL</b>.

## Remarks

<b>ExInterlockedInsertTailList</b> performs the same operation as <a href="..\wdm\nf-wdm-inserttaillist.md">InsertTailList</a>, but atomically. Do not mix atomic and non-atomic calls on the same list.

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

<a href="..\wdm\nf-wdm-inserttaillist.md">InsertTailList</a>



<a href="..\wdm\nf-wdm-exinterlockedinsertheadlist.md">ExInterlockedInsertHeadList</a>



<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>



<a href="..\wdm\nf-wdm-initializelisthead.md">InitializeListHead</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInterlockedInsertTailList routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>