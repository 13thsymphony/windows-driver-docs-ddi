---
UID: NF:fltkernel.FltReleasePushLock
title: FltReleasePushLock macro
author: windows-driver-content
description: The FltReleasePushLock routine releases a specified push lock owned by the current thread.
old-location: ifsk\fltreleasepushlock.htm
old-project: ifsk
ms.assetid: 34d1b945-329c-47ff-913d-5576eef665b8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_p_to_z_31e736a4-7790-443f-a6bf-e43d3823ad27.xml, FltReleasePushLock, FltReleasePushLock routine [Installable File System Drivers], fltkernel/FltReleasePushLock, ifsk.fltreleasepushlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltReleasePushLock
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltReleasePushLock function
The <b>FltReleasePushLock</b> routine releases a specified push lock owned by the current thread.

## Syntax

````
VOID FltReleasePushLock(
  _Inout_ PEX_PUSH_LOCK PushLock
);
````

## Parameters

`Lock`

TBD


## Return Value

None

## Remarks

<b>FltReleasePushLock</b> releases a push lock that was previously acquired by calling <a href="..\fltkernel\nf-fltkernel-fltacquirepushlockexclusive.md">FltAcquirePushLockExclusive</a> or <a href="..\fltkernel\nf-fltkernel-fltacquirepushlockshared.md">FltAcquirePushLockShared</a>. 

Because <b>FltReleasePushLock</b> reenables normal kernel APC delivery, it is not necessary to call <a href="..\wdm\nf-wdm-keleavecriticalregion.md">KeLeaveCriticalRegion</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545908">FsRtlExitFileSystem</a> after calling <b>FltReleasePushLock</b>. 

For more information about push locks, see the reference entry for <a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>. 

To acquire a push lock for exclusive access, call <a href="..\fltkernel\nf-fltkernel-fltacquirepushlockexclusive.md">FltAcquirePushLockExclusive</a>. 

To acquire a push lock for shared access, call <a href="..\fltkernel\nf-fltkernel-fltacquirepushlockshared.md">FltAcquirePushLockShared</a>. 

To initialize a push lock, call <a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>. 

To delete a push lock, call <a href="..\fltkernel\nf-fltkernel-fltdeletepushlock.md">FltDeletePushLock</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later.  |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltacquirepushlockshared.md">FltAcquirePushLockShared</a>



<a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>



<a href="..\fltkernel\nf-fltkernel-fltacquirepushlockexclusive.md">FltAcquirePushLockExclusive</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletepushlock.md">FltDeletePushLock</a>



<a href="..\wdm\nf-wdm-keleavecriticalregion.md">KeLeaveCriticalRegion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545908">FsRtlExitFileSystem</a>