---
UID : NF:ndis.NdisReleaseSpinLock
title : NdisReleaseSpinLock macro
author : windows-driver-content
description : The NdisReleaseSpinLock function releases a spin lock that was acquired in a preceding call to the NdisAcquireSpinLock function.
old-location : netvista\ndisreleasespinlock.htm
old-project : netvista
ms.assetid : dd833373-2879-49f0-9b16-fddb2f7495c1
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.ndisreleasespinlock, NdisReleaseSpinLock macro [Network Drivers Starting with Windows Vista], ndis_spin_lock_ref_a4e1c783-4682-401c-a198-fdc14cbfa383.xml, ndis/NdisReleaseSpinLock, NdisReleaseSpinLock
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReleaseSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReleaseSpinLock (NDIS   5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_Synch_Function, SpinLock, SpinLockBalanced, SpinLockDpr, SpinLockDprRelease, SpinlockRelease
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisReleaseSpinLock function
The 
  <b>NdisReleaseSpinLock</b> function releases a spin lock that was acquired in a preceding call to the 
  <a href="..\ndis\nf-ndis-ndisacquirespinlock.md">NdisAcquireSpinLock</a> function.

## Syntax

````
VOID NdisReleaseSpinLock(
  [in] PNDIS_SPIN_LOCK SpinLock
);
````

## Parameters

`_SpinLock`

Pointer to the acquired spin lock to be released.


## Return Value

None

## Remarks

A driver must initialize its spin lock with 
    <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> before it calls
    any other 
    <b>Ndis..SpinLock</b> function to access the resources protected by that spin lock.

A driver must call 
    <a href="..\ndis\nf-ndis-ndisacquirespinlock.md">NdisAcquireSpinLock</a> to acquire the
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
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/synchronization-and-notification-in-network-drivers">Synchronization
    and Notification in Network Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReleaseSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReleaseSpinLock (NDIS   5.1)) in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReleaseSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReleaseSpinLock (NDIS   5.1)) in Windows XP. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** | Irql_Synch_Function, SpinLock, SpinLockBalanced, SpinLockDpr, SpinLockDprRelease, SpinlockRelease |

## See Also

<a href="..\ndis\nf-ndis-ndisacquirespinlock.md">NdisAcquireSpinLock</a>

<a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a>

<a href="..\ndis\nf-ndis-ndisdpracquirespinlock.md">NdisDprAcquireSpinLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisReleaseSpinLock macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>