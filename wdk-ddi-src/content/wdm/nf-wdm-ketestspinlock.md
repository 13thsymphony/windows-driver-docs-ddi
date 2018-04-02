---
UID: NF:wdm.KeTestSpinLock
title: KeTestSpinLock function
author: windows-driver-content
description: The KeTestSpinLock routine tests for the availability of a spin lock.
old-location: kernel\ketestspinlock.htm
old-project: kernel
ms.assetid: 5386349c-b4b8-43db-8f66-70dc7e71345e
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeTestSpinLock, KeTestSpinLock routine [Kernel-Mode Driver Architecture], k105_99f18fd9-0242-4939-86ab-016236f9adcb.xml, kernel.ketestspinlock, wdm/KeTestSpinLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeTestSpinLock
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeTestSpinLock function
The <b>KeTestSpinLock</b> routine tests for the availability of a spin lock.

## Syntax

```
NTKERNELAPI BOOLEAN KeTestSpinLock(
  PKSPIN_LOCK SpinLock
);
```

## Parameters

`SpinLock`

A pointer to a spin lock. The spin lock must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>.


## Return Value

<b>KeTestSpinLock</b> returns <b>FALSE</b> if the spin lock is currently being held. Otherwise, it returns <b>TRUE</b>.

## Remarks

This routine enables the caller that is running at a low IRQL to test the spin lock. If <b>KeTestSpinLock</b> returns <b>TRUE</b>, the caller can try to acquire the spin lock with a high probability of immediate success.

This routine neither raises nor lowers the IRQL, and it never acquires the spin lock.

For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2003 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | See Remarks section. |
| **DDI compliance rules** | HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551917">KeAcquireSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553145">KeReleaseSpinLock</a>