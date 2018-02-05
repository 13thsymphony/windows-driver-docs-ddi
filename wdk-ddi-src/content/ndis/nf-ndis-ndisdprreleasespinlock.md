---
UID : NF:ndis.NdisDprReleaseSpinLock
title : NdisDprReleaseSpinLock macro
author : windows-driver-content
description : The NdisDprReleaseSpinLock function releases a spin lock acquired in the immediately preceding call to the NdisDprAcquireSpinLock function.
old-location : netvista\ndisdprreleasespinlock.htm
old-project : netvista
ms.assetid : d6a7af70-6a1e-471b-919f-80a704d25446
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis/NdisDprReleaseSpinLock, NdisDprReleaseSpinLock, NdisDprReleaseSpinLock macro [Network Drivers Starting with Windows Vista], ndis_spin_lock_ref_7f9e73b2-9284-4a8c-895e-209a7685fa94.xml, netvista.ndisdprreleasespinlock
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisDprReleaseSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisDprReleaseSpinLock (NDIS   5.1)) in Windows XP.
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


# NdisDprReleaseSpinLock function
The 
  <b>NdisDprReleaseSpinLock</b> function releases a spin lock acquired in the immediately preceding call to
  the 
  <a href="..\ndis\nf-ndis-ndisdpracquirespinlock.md">
  NdisDprAcquireSpinLock</a> function.

## Syntax

````
VOID NdisDprReleaseSpinLock(
  [in] PNDIS_SPIN_LOCK SpinLock
);
````

## Parameters

`_SpinLock`

Pointer to the acquired spin lock to be released.


## Return Value

None

## Remarks

Release of the spin lock allows another driver function to use the resources the lock protects after
    that function acquires the spin lock.

A spin lock acquired with 
    <b>NdisDprAcquireSpinLock</b> must be released with 
    <b>NdisDprReleaseSpinLock</b>. A spin lock acquired with 
    <a href="..\ndis\nf-ndis-ndisacquirespinlock.md">NdisAcquireSpinLock</a> must be released
    with 
    <a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a>.

For more information about acquiring and releasing NDIS spin locks, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/synchronization-and-notification-in-network-drivers">Synchronization
    and Notification in Network Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisDprReleaseSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisDprReleaseSpinLock (NDIS   5.1)) in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisDprReleaseSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisDprReleaseSpinLock (NDIS   5.1)) in Windows XP. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** | Irql_Synch_Function, SpinLock, SpinLockBalanced, SpinLockDpr, SpinLockDprRelease, SpinlockRelease |

## See Also

<a href="..\ndis\nf-ndis-ndisdpracquirespinlock.md">NdisDprAcquireSpinLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisDprReleaseSpinLock macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>