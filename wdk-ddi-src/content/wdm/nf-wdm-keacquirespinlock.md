---
UID: NF:wdm.KeAcquireSpinLock
title: KeAcquireSpinLock macro
author: windows-driver-content
description: The KeAcquireSpinLock routine acquires a spin lock so the caller can synchronize access to shared data in a multiprocessor-safe way by raising IRQL.
old-location: kernel\keacquirespinlock.htm
old-project: kernel
ms.assetid: 10999175-4793-4045-8a74-a9a491724ec9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeAcquireSpinLock
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
req.alt-api: KeAcquireSpinLock
req.alt-loc: Hal.lib,Hal.dll
req.ddi-compliance: IrqlKeDispatchLte, MarkingQueuedIrps, SpinLock, SpinLockDpc, SpinlockRelease, SpinLockSafe, ReqSendWhileSpinlock, Spinlock(kmdf), SpinlockDpc(kmdf), SpinlockRelease(kmdf), HwStorPortProhibitedDDIs, SpinLock(storport), SpinLockDpc(storport), SpinLockRelease(storport), SpinLockSafe(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeAcquireSpinLock macro



## -description
The <b>KeAcquireSpinLock</b> routine acquires a spin lock so the caller can synchronize access to shared data in a multiprocessor-safe way by raising IRQL.



## -syntax

````
VOID KeAcquireSpinLock(
  _In_  PKSPIN_LOCK SpinLock,
  _Out_ PKIRQL      OldIrql
);
````


## -parameters

### -param SpinLock [in]

Pointer to an initialized spin lock for which the caller provides the storage.


### -param OldIrql [out]

Pointer to a variable that is set to the current IRQL when this call occurs.


## -remarks
<b>KeAcquireSpinLock</b> first resets the IRQL to DISPATCH_LEVEL and then acquires the lock. The previous IRQL is written to <i>OldIrql</i> after the lock is acquired.

The <i>OldIrql</i> value must be specified when the spin lock is released with <a href="..\wdm\nf-wdm-kereleasespinlock.md">KeReleaseSpinLock</a>.

Most drivers use a local variable to store the old IRQL value. A driver can also use a shared memory location, such as a global variable, but the driver must not use the same location for two different locks. Otherwise, a race condition can occur.

Spin locks can cause serious problems if not used judiciously. In particular, no deadlock protection is performed and dispatching is disabled while the spin lock is held. Therefore:

The code within a critical region guarded by an spin lock must neither be pageable nor make any references to pageable data.

The code within a critical region guarded by a spin lock can neither call any external function that might access pageable data or raise an exception, nor can it generate any exceptions.

The caller should release the spin lock with <b>KeReleaseSpinLock</b> as quickly as possible.

Attempting to acquire a spin lock recursively is guaranteed to cause a deadlock. For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Hal.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547812">IrqlKeDispatchLte</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549016">MarkingQueuedIrps</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/dn926953">SpinLock</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff819089">SpinLockDpc</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454251">SpinlockRelease</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454252">SpinLockSafe</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff551602">ReqSendWhileSpinlock</a>, <a href="https://msdn.microsoft.com/911E4350-851F-4AC4-B982-B2B4B974C243">Spinlock(kmdf)</a>, <a href="https://msdn.microsoft.com/77DA365C-7717-45B6-B8AD-9686B880AB50">SpinlockDpc(kmdf)</a>, <a href="https://msdn.microsoft.com/23BEB857-309D-4C11-A361-D72F87C84154">SpinlockRelease(kmdf)</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>, <a href="https://msdn.microsoft.com/7D06327F-CE74-4337-8B5C-79189FE15F2F">SpinLock(storport)</a>, <a href="https://msdn.microsoft.com/955B5A37-5E14-4380-A30D-3D019C4D5B59">SpinLockDpc(storport)</a>, <a href="https://msdn.microsoft.com/CD4287CB-EF0C-476C-BF10-B46B96AB7D11">SpinLockRelease(storport)</a>, <a href="https://msdn.microsoft.com/12D36178-C00D-44A7-9DA0-E0663DF1FFDC">SpinLockSafe(storport)</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551899">KeAcquireInStackQueuedSpinLock</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keacquirespinlockatdpclevel.md">KeAcquireSpinLockAtDpcLevel</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kereleasespinlock.md">KeReleaseSpinLock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeAcquireSpinLock routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

