---
UID: NF:wdm.KeAcquireSpinLockAtDpcLevel
title: KeAcquireSpinLockAtDpcLevel macro
author: windows-driver-content
description: The KeAcquireSpinLockAtDpcLevel routine acquires a spin lock when the caller is already running at IRQL &gt;= DISPATCH_LEVEL.
old-location: kernel\keacquirespinlockatdpclevel.htm
old-project: kernel
ms.assetid: 010b5e42-26c7-433f-b67b-1afdc0ec564c
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeAcquireSpinLockAtDpcLevel, KeAcquireSpinLockAtDpcLevel routine [Kernel-Mode Driver Architecture], KefAcquireSpinLockAtDpcLevel, k105_4b7eb718-f04d-42de-9dfc-92355cd2ebc9.xml, kernel.keacquirespinlockatdpclevel, wdm/KeAcquireSpinLockAtDpcLevel, wdm/KefAcquireSpinLockAtDpcLevel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs, IrqlDispatch, SpinLockSafe
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
-	KeAcquireSpinLockAtDpcLevel
-	KefAcquireSpinLockAtDpcLevel
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeAcquireSpinLockAtDpcLevel function
The <b>KeAcquireSpinLockAtDpcLevel</b> routine acquires a spin lock when the caller is already running at IRQL &gt;= DISPATCH_LEVEL.

## Syntax

````
VOID KeAcquireSpinLockAtDpcLevel(
  _Inout_ PKSPIN_LOCK SpinLock
);
````

## Parameters

`a`

TBD


## Return Value

None

## Remarks

Drivers call <b>KeAcquireSpinLockAtDpcLevel</b> instead of <a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a> for better driver performance if and only if they are already running at an IRQL of DISPATCH_LEVEL or above.

If a driver is running at IRQL &lt;= APC_LEVEL, it should call <b>KeAcquireSpinLock</b> to have IRQL raised by that routine. <b>KeAcquireSpinLockAtDpcLevel</b> assumes the caller is already running at IRQL &gt;= DISPATCH_LEVEL, so no raise is necessary.

The caller should release the spin lock with <a href="..\wdm\nf-wdm-kereleasespinlockfromdpclevel.md">KeReleaseSpinLockFromDpcLevel</a> as quickly as possible.

For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | See Remarks section. |
| **DDI compliance rules** | HwStorPortProhibitedDDIs, IrqlDispatch, SpinLockSafe |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551908">KeAcquireInStackQueuedSpinLockAtDpcLevel</a>



<a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a>



<a href="..\wdm\nf-wdm-kereleasespinlockfromdpclevel.md">KeReleaseSpinLockFromDpcLevel</a>



<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>



<a href="..\wdm\nf-wdm-kereleasespinlock.md">KeReleaseSpinLock</a>



<a href="..\wdm\nf-wdm-ketrytoacquirespinlockatdpclevel.md">KeTryToAcquireSpinLockAtDpcLevel</a>