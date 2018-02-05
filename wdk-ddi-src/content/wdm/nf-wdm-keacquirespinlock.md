---
UID : NF:wdm.KeAcquireSpinLock
title : KeAcquireSpinLock macro
author : windows-driver-content
description : The KeAcquireSpinLock routine acquires a spin lock so the caller can synchronize access to shared data in a multiprocessor-safe way by raising IRQL.
old-location : kernel\keacquirespinlock.htm
old-project : kernel
ms.assetid : 10999175-4793-4045-8a74-a9a491724ec9
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : k105_387b61b6-b20f-4f17-be47-74c9ed3ac8a1.xml, wdm/KeAcquireSpinLock, KeAcquireSpinLock, kernel.keacquirespinlock, KeAcquireSpinLock routine [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : IrqlKeDispatchLte, MarkingQueuedIrps, SpinLock, SpinLockDpc, SpinlockRelease, SpinLockSafe, ReqSendWhileSpinlock, Spinlock(kmdf), SpinlockDpc(kmdf), SpinlockRelease(kmdf), HwStorPortProhibitedDDIs, SpinLock(storport), SpinLockDpc(storport), SpinLockRelease(storport), SpinLockSafe(storport)
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Hal.lib
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# KeAcquireSpinLock function
The <b>KeAcquireSpinLock</b> routine acquires a spin lock so the caller can synchronize access to shared data in a multiprocessor-safe way by raising IRQL.

## Syntax

````
VOID KeAcquireSpinLock(
  _In_  PKSPIN_LOCK SpinLock,
  _Out_ PKIRQL      OldIrql
);
````

## Parameters

`a`

TBD

`b`

TBD


## Return Value

None

## Remarks

<b>KeAcquireSpinLock</b> first resets the IRQL to DISPATCH_LEVEL and then acquires the lock. The previous IRQL is written to <i>OldIrql</i> after the lock is acquired.

The <i>OldIrql</i> value must be specified when the spin lock is released with <a href="..\wdm\nf-wdm-kereleasespinlock.md">KeReleaseSpinLock</a>.

Most drivers use a local variable to store the old IRQL value. A driver can also use a shared memory location, such as a global variable, but the driver must not use the same location for two different locks. Otherwise, a race condition can occur.

Spin locks can cause serious problems if not used judiciously. In particular, no deadlock protection is performed and dispatching is disabled while the spin lock is held. Therefore:
<ul>
<li>
The code within a critical region guarded by an spin lock must neither be pageable nor make any references to pageable data.

</li>
<li>
The code within a critical region guarded by a spin lock can neither call any external function that might access pageable data or raise an exception, nor can it generate any exceptions.

</li>
<li>
The caller should release the spin lock with <b>KeReleaseSpinLock</b> as quickly as possible.

</li>
</ul>Attempting to acquire a spin lock recursively is guaranteed to cause a deadlock. For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | Hal.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | IrqlKeDispatchLte, MarkingQueuedIrps, SpinLock, SpinLockDpc, SpinlockRelease, SpinLockSafe, ReqSendWhileSpinlock, Spinlock(kmdf), SpinlockDpc(kmdf), SpinlockRelease(kmdf), HwStorPortProhibitedDDIs, SpinLock(storport), SpinLockDpc(storport), SpinLockRelease(storport), SpinLockSafe(storport) |

## See Also

<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>

<a href="..\wdm\nf-wdm-keacquirespinlockatdpclevel.md">KeAcquireSpinLockAtDpcLevel</a>

<a href="..\wdm\nf-wdm-kereleasespinlock.md">KeReleaseSpinLock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551899">KeAcquireInStackQueuedSpinLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeAcquireSpinLock routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>