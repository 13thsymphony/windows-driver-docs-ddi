---
UID: NF.ndis.NdisReleaseSpinLock
title: NdisReleaseSpinLock macro
author: windows-driver-content
description: The NdisReleaseSpinLock function releases a spin lock that was acquired in a preceding call to the NdisAcquireSpinLock function.
old-location: netvista\ndisreleasespinlock.htm
old-project: netvista
ms.assetid: dd833373-2879-49f0-9b16-fddb2f7495c1
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisReleaseSpinLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReleaseSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReleaseSpinLock (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisReleaseSpinLock
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Synch_Function, SpinLock, SpinLockBalanced, SpinLockDpr, SpinLockDprRelease, SpinlockRelease
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: DISPATCH_LEVEL
---

# NdisReleaseSpinLock macro



## -description
The 
  <b>NdisReleaseSpinLock</b> function releases a spin lock that was acquired in a preceding call to the 
  <a href="netvista.ndisacquirespinlock">NdisAcquireSpinLock</a> function.



## -syntax

````
VOID NdisReleaseSpinLock(
  [in] PNDIS_SPIN_LOCK SpinLock
);
````


## -parameters

### -param SpinLock [in]

Pointer to the acquired spin lock to be released.


## -remarks
A driver must initialize its spin lock with 
    <a href="netvista.ndisallocatespinlock">NdisAllocateSpinLock</a> before it calls
    any other 
    <b>Ndis..SpinLock</b> function to access the resources protected by that spin lock.

A driver must call 
    <a href="netvista.ndisacquirespinlock">NdisAcquireSpinLock</a> to acquire the
    spin lock before it can call 
    <b>NdisReleaseSpinLock</b>. Each call to 
    <b>NdisAcquireSpinLock</b> requires a reciprocal call to 
    <b>NdisReleaseSpinLock</b> before the driver can call 
    <b>NdisAcquireSpinLock</b> again.

<b>NdisReleaseSpinLock</b> restores the original IRQL at which its caller was running before the call to 
    <b>NdisAcquireSpinLock</b>.

Any spin lock acquired with 
    <b>NdisAcquireSpinLock</b> must be released with 
    <b>NdisReleaseSpinLock</b>. Any spin lock acquired with 
    <b>NdisDprAcquireSpinLock</b> must be released with 
    <b>NdisDprReleaseSpinLock</b>.

For more information about acquiring and releasing NDIS spin locks, see 
    <a href="netvista.synchronization_and_notification_in_network_drivers">Synchronization
    and Notification in Network Drivers</a>.


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
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/fe764786-7ab5-4b56-8f86-19010d0535af">NdisReleaseSpinLock (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisReleaseSpinLock (NDIS
   5.1)</b>) in Windows XP.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_synch_function">Irql_Synch_Function</a>, <a href="devtest.ndis_spinlock">SpinLock</a>, <a href="devtest.ndis_spinlockbalanced">SpinLockBalanced</a>, <a href="devtest.ndis_spinlockdpr">SpinLockDpr</a>, <a href="devtest.ndis_spinlockdprrelease">SpinLockDprRelease</a>, <a href="devtest.ndis_spinlockrelease">SpinlockRelease</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndisacquirespinlock">NdisAcquireSpinLock</a>
</dt>
<dt>
<a href="netvista.ndisallocatespinlock">NdisAllocateSpinLock</a>
</dt>
<dt>
<a href="netvista.ndisdpracquirespinlock">NdisDprAcquireSpinLock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisReleaseSpinLock macro%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

