---
UID: NF:wdm.ExInterlockedAddLargeInteger
title: ExInterlockedAddLargeInteger function
author: windows-driver-content
description: The ExInterlockedAddLargeInteger routine adds a large integer value to the specified variable as an atomic operation.
old-location: kernel\exinterlockedaddlargeinteger.htm
old-project: kernel
ms.assetid: ace8405b-74a7-4797-8d3d-3caf673dace2
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExInterlockedAddLargeInteger, ExInterlockedAddLargeInteger routine [Kernel-Mode Driver Architecture], k102_934a3a64-9f63-402c-8b55-db7e2b4d9d4b.xml, kernel.exinterlockedaddlargeinteger, wdm/ExInterlockedAddLargeInteger
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows. Not available in Windows 98 or Windows Me.
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
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExInterlockedAddLargeInteger
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExInterlockedAddLargeInteger function
The <b>ExInterlockedAddLargeInteger</b> routine adds a large integer value to the specified variable as an atomic operation.

## Syntax

```
NTKERNELAPI LARGE_INTEGER ExInterlockedAddLargeInteger(
  PLARGE_INTEGER                               Addend,
  LARGE_INTEGER                                Increment,
  _Requires_lock_not_held_(*_Curr_)PKSPIN_LOCK Lock
);
```

## Parameters

`Addend`

A pointer to the variable to be adjusted by the <i>Increment</i> value.

`Increment`

Specifies a value to be added to <i>Addend</i>.

`Lock`

A pointer to a spin lock to be used to synchronize access to <i>Addend</i>.


## Return Value

<b>ExInterlockedAddLargeInteger</b> returns the initial value of the <i>Addend </i>parameter.

## Remarks

Support routines that do interlocked operations are assumed to be incapable of causing a page fault. That is, neither their code nor any of the data they touch can cause a page fault without bringing down the system. They use spin locks to achieve atomicity on symmetric multiprocessor machines. The caller must provide resident storage for the <i>Lock</i>, which must be initialized with <b>KeInitializeSpinLock</b> before the initial call to an <b>ExInterlocked<i>Xxx</i></b>.

The <i>Lock</i> passed to <b>ExInterlockedAddLargeInteger</b> is used to assure that the add operation on <i>Addend</i> is atomic with respect to any other operations on the same value which synchronize with this same spin lock. 

<b>ExInterlockedAddLargeInteger</b> masks interrupts. Consequently, it can be used for synchronization between an ISR and other device driver code, provided that the same <i>Lock</i> is never reused in a call to a routine that runs at IRQL = DISPATCH_LEVEL.

Note that calls to <b>Interlocked<i>Xxx</i></b> are guaranteed to be atomic with respect to other <b>Interlocked<i>Xxx</i></b> calls without caller-supplied spin locks.

Callers of <b>ExInterlockedAddLargeInteger</b> run at any IRQL. The storage for the <i>Addend</i> parameter must be resident at all IRQLs.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of Windows. Not available in Windows 98 or Windows Me.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level (see Remarks section) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545343">ExInterlockedAddUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547871">InterlockedDecrement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547910">InterlockedIncrement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>