---
UID : NF:ndis.NdisDprAcquireSpinLock
title : NdisDprAcquireSpinLock macro
author : windows-driver-content
description : The NdisDprAcquireSpinLock function acquires a spin lock so the caller can synchronize access to resources shared among non-ISR driver functions in a multiprocessor-safe way.
old-location : netvista\ndisdpracquirespinlock.htm
old-project : netvista
ms.assetid : 2e21d2f8-467e-43d3-8261-2373a8b8daa4
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisDprAcquireSpinLock, NdisDprAcquireSpinLock macro [Network Drivers Starting with Windows Vista], ndis/NdisDprAcquireSpinLock, ndis_spin_lock_ref_c954c605-2544-4911-8ebd-ba0464228437.xml, netvista.ndisdpracquirespinlock
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisDprAcquireSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisDprAcquireSpinLock (NDIS   5.1)) in Windows XP.
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


# NdisDprAcquireSpinLock function
The 
  <b>NdisDprAcquireSpinLock</b> function acquires a spin lock so the caller can synchronize access to
  resources shared among non-ISR driver functions in a multiprocessor-safe way.

## Syntax

````
VOID NdisDprAcquireSpinLock(
  [in] PNDIS_SPIN_LOCK SpinLock
);
````

## Parameters

`_SpinLock`

TBD


## Return Value

None

## Remarks

The miniport driver must initialize a variable of type NDIS_SPIN_LOCK with 
    <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> before it calls
    any other 
    <b>Ndis..SpinLock</b> function. The driver must provide resident storage for the spin lock(s) it uses.

<b>NdisDprAcquireSpinLock</b> is an optimized version of 
    <a href="..\ndis\nf-ndis-ndisacquirespinlock.md">NdisAcquireSpinLock</a> that a miniport
    driver can call only while running at IRQL = DISPATCH_LEVEL.

After acquiring a spin lock with 
    <b>NdisDprAcquireSpinLock</b>, the caller must release that lock with a call to 
    <a href="..\ndis\nf-ndis-ndisdprreleasespinlock.md">NdisDprReleaseSpinLock</a>. A miniport
    driver must call 
    <b>NdisDprReleaseSpinLock</b> following each call to 
    <b>NdisDprAcquireSpinLock</b>. Otherwise, a deadlock occurs, hanging the driver.

A spin lock acquired with 
    <b>NdisDprAcquireSpinLock</b> must be released with 
    <b>NdisDprReleaseSpinLock</b>. A spin lock acquired with 
    <b>NdisAcquireSpinLock</b> must be released with 
    <b>NdisReleaseSpinLock</b>.

A driver should never hold a spin lock for an extended period (more than a few instructions). Holding
    a spin lock for longer than 25 microseconds degrades both system and driver performance.

A miniport driver cannot use a spin lock to protect resources that its other functions share with the 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> and/or 
    <mshelp:link keywords="netvista.miniportdisableinterruptex" tabindex="0"><i>
    MiniportDisableInterruptEx</i></mshelp:link> functions. Instead, a miniport driver must call 
    <mshelp:link keywords="netvista.ndismsynchronizewithinterruptex" tabindex="0"><b>
    NdisMSynchronizeWithInterruptEx</b></mshelp:link> so that its 
    <mshelp:link keywords="netvista.miniportsynchronizeinterrupt" tabindex="0"><i>
    MiniportSynchronizeInterrupt</i></mshelp:link> function accesses such shared resources at the same DIRQL at which its
    
    <i>MiniportInterrupt</i> and/or 
    <i>MiniportDisableInterruptEx</i> functions do.

For more information about acquiring and releasing NDIS spin locks, see 
    <mshelp:link keywords="netvista.synchronization_and_notification_in_network_drivers" tabindex="0">Synchronization
    and Notification in Network Drivers</mshelp:link>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** | Irql_Synch_Function, SpinLock, SpinLockBalanced, SpinLockDpr, SpinLockDprRelease, SpinlockRelease |

## See Also

<mshelp:link keywords="netvista.miniportsynchronizeinterrupt" tabindex="0"><i>
   MiniportSynchronizeInterrupt</i></mshelp:link>

<a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a>

<a href="..\ndis\nc-ndis-miniport_disable_interrupt.md">MiniportDisableInterruptEx</a>

<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>

<a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a>

<a href="..\ndis\nf-ndis-ndisdprreleasespinlock.md">NdisDprReleaseSpinLock</a>

<mshelp:link keywords="netvista.ndismsynchronizewithinterruptex" tabindex="0"><b>
   NdisMSynchronizeWithInterruptEx</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndisacquirespinlock.md">NdisAcquireSpinLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisDprAcquireSpinLock macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>