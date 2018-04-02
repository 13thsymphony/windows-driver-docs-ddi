---
UID: NF:wdm.KeInitializeSpinLock
title: KeInitializeSpinLock function
author: windows-driver-content
description: The KeInitializeSpinLock routine initializes a variable of type KSPIN_LOCK.
old-location: kernel\keinitializespinlock.htm
old-project: kernel
ms.assetid: 84962db0-55ed-443c-84e3-2d8f3e9ec1d7
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeInitializeSpinLock, KeInitializeSpinLock routine [Kernel-Mode Driver Architecture], k105_715eff59-827a-4d41-8e3a-2ce0d1f1181d.xml, kernel.keinitializespinlock, wdm/KeInitializeSpinLock
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
req.ddi-compliance: HwStorPortProhibitedDDIs
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
-	KeInitializeSpinLock
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeInitializeSpinLock function
The <b>KeInitializeSpinLock </b>routine initializes a variable of type KSPIN_LOCK.

## Syntax

```
NTKERNELAPI VOID KeInitializeSpinLock(
  PKSPIN_LOCK SpinLock
);
```

## Parameters

`SpinLock`

Pointer to a spin lock, for which the caller must provide the storage.


## Return Value

None

## Remarks

This routine must be called before an initial call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551917">KeAcquireSpinLock</a>, to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551899">KeAcquireInStackQueuedSpinLock</a>, or to any other support routine that requires a spin lock as an argument.

Storage for a spin lock object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.

Callers of this routine can be running at any IRQL. Usually, a caller is running at IRQL = PASSIVE_LEVEL in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level (see Remarks section) |
| **DDI compliance rules** | HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551899">KeAcquireInStackQueuedSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551908">KeAcquireInStackQueuedSpinLockAtDpcLevel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551917">KeAcquireSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551921">KeAcquireSpinLockAtDpcLevel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553130">KeReleaseInStackQueuedSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553137">KeReleaseInStackQueuedSpinLockFromDpcLevel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553145">KeReleaseSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553150">KeReleaseSpinLockFromDpcLevel</a>