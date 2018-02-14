---
UID: NF:ndis.NdisAllocateRWLock
title: NdisAllocateRWLock function
author: windows-driver-content
description: The NdisAllocateRWLock function allocates a read/write lock variable of type NDIS_RW_LOCK_EX.
old-location: netvista\ndisallocaterwlock.htm
old-project: netvista
ms.assetid: 460c81bf-ae06-40f7-a019-b006e5c9f94b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisallocaterwlock, ndis/NdisAllocateRWLock, NdisAllocateRWLock, ndis_processor_group_ref_7df54f29-88d4-4596-9649-8af7b84f6d7e.xml, NdisAllocateRWLock function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisAllocateRWLock
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisAllocateRWLock function
The 
  <b>NdisAllocateRWLock</b> function allocates a read/write lock variable of type 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a>.

## Syntax

````
PNDIS_RW_LOCK_EX NdisAllocateRWLock(
   NDIS_HANDLE NdisHandle
);
````

## Parameters

`NdisHandle`

A handle returned from one of the following functions:
     

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
<b>Windows 8 and Windows Server 2012 and later:  </b>If the read/write lock is being allocated in <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> before any NDIS handle is available, the caller may pass a NULL value for this parameter.


## Return Value

<b>NdisAllocateRWLock</b> returns a pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> structure if one can be allocated; otherwise it returns <b>NULL</b>.

## Remarks

NDIS drivers call the 
    <b>NdisAllocateRWLock</b> function to allocate an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> structure that controls
    read/write access to resources that are shared among driver threads. Drivers use a read/write lock for
    resources that are frequently accessed for reading and infrequently accessed for writing.

Each lock that a driver allocates can do one of the following:

<ul>
<li>
Protect a discrete set of shared resources from concurrent write and read access by driver threads
      that run at IRQL &lt;= DISPATCH_LEVEL.

</li>
<li>
Expose a discrete set of shared resources to concurrent read access by driver threads that run at
      IRQL &lt;= DISPATCH_LEVEL.

</li>
</ul>
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> pointer that 
    <b>NdisAllocateRWLock</b> returns is a required parameter for all other read/write lock functions.

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> is not fair.  That is, a processor waiting to acquire the lock for exclusive access may be starved by processors that hold the lock for read access.  Therefore, do not use an <b>NDIS_RW_LOCK_EX</b> in situations where the majority of accesses will be for write access.  If the majority of accesses will need write access, it is more efficient to simply use a kernel spin lock. For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548114">Introduction to Spin Locks</a>.

In situations where there are many acquisitions for read access on more than one processor, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> typically performs better than a kernel spin lock.  Use <b>NDIS_RW_LOCK_EX</b> when you expect many read accesses per second distributed across more than one processor.

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> structure defines attributes that limit write access to shared resources to one
    non-ISR driver thread at a time. The <b>NDIS_RW_LOCK_EX</b> structure can allow multiple non-ISR driver threads
    to have concurrent read access to the associated resources. Such read access is not permitted during a
    write access.

To modify the protected resources, a driver thread must obtain a write lock with the 
    <a href="..\ndis\nf-ndis-ndisacquirerwlockwrite.md">NdisAcquireRWLockWrite</a> function. To
    simply read those resources, a driver thread must obtain a read-only lock with the 
    <a href="..\ndis\nf-ndis-ndisacquirerwlockread.md">NdisAcquireRWLockRead</a> function. Read
    access does not require interlocked operations or contention for spin locks. Read-only access helps
    maintain good operating system and driver performance.

After the resource access is complete, the driver calls the 
    <a href="..\ndis\nf-ndis-ndisreleaserwlock.md">NdisReleaseRWLock</a> function.

A driver must call the 
    <a href="..\ndis\nf-ndis-ndisfreerwlock.md">NdisFreeRWLock</a> function to free the
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> structure that it allocated with the 
    <b>NdisAllocateRWLock</b> function.

You can use the <b>!ndiskd.ndisrwlock</b> debugger extension to inspect an <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a>, see how many readers it has, and see who its current writer is. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552270">NDIS Extensions (Ndiskd.dll)</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later. Supported in NDIS 6.20 and later. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548114">Introduction to Spin Locks</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>



<a href="..\ndis\nf-ndis-ndisfreerwlock.md">NdisFreeRWLock</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisacquirerwlockread.md">NdisAcquireRWLockRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552270">NDIS Extensions (Ndiskd.dll)</a>



<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



<a href="..\ndis\nf-ndis-ndisreleaserwlock.md">NdisReleaseRWLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a>



<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\nf-ndis-ndisacquirerwlockwrite.md">NdisAcquireRWLockWrite</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateRWLock function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>