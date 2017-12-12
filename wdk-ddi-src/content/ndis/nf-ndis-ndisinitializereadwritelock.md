---
UID: NF.ndis.NdisInitializeReadWriteLock
title: NdisInitializeReadWriteLock function
author: windows-driver-content
description: The NdisInitializeReadWriteLock function initializes a read or write lock variable of type NDIS_RW_LOCK.Note  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use NdisAllocateRWLock instead of NdisInitializeReadWriteLock.
old-location: netvista\ndisinitializereadwritelock.htm
old-project: netvista
ms.assetid: 458d8a08-7212-4888-9bb3-07a470541c8d
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisInitializeReadWriteLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Deprecated for NDIS 6.20 and later drivers, which should use NdisAllocateRWLock instead of NdisInitializeReadWriteLock. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInitializeReadWriteLock   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInitializeReadWriteLock   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisInitializeReadWriteLock
req.alt-loc: ndis.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: Ndis.sys
req.irql: Any level (see Remarks section)
---

# NdisInitializeReadWriteLock function



## -description
The
  <b>NdisInitializeReadWriteLock</b> function initializes a read or write lock variable of type 
  <b>NDIS_RW_LOCK</b>.



## -syntax

````
VOID NdisInitializeReadWriteLock(
  _Out_ PNDIS_RW_LOCK Lock
);
````


## -parameters

### -param Lock [out]

A pointer to an opaque 
     <b>NDIS_RW_LOCK</b> variable that represents a lock. The caller can use this lock to gain write or read
     access to resources that are shared among non-ISR driver threads.


## -returns
None


## -remarks
An 
    <b>NDIS_RW_LOCK</b> variable is used to limit write access to shared resources to one non-ISR driver
    thread at a time. This 
    <b>NDIS_RW_LOCK</b> can allow multiple non-ISR driver threads concurrent read access to those resources.
    Such read access is not permitted during a write access.

The 
    <i>Lock</i> pointer that is passed to 
    <b>NdisInitializeReadWriteLock</b> is a required parameter for all other 
    <b>Ndis..ReadWriteLock</b> functions.

Before a driver calls the 
    <a href="netvista.ndisacquirereadwritelock">NdisAcquireReadWriteLock</a> function
    to obtain write or read access to a resource, the driver must call 
    <b>NdisInitializeReadWriteLock</b> to initialize the lock that is associated with that resource. The
    caller must provide nonpaged storage for the variable at 
    <i>Lock</i> .

After calling 
    <b>NdisInitializeReadWriteLock</b>, the driver can call 
    <a href="netvista.ndisacquirereadwritelock">NdisAcquireReadWriteLock</a> to obtain either write or read access to the resource. Only one non-ISR
    driver thread at a time can obtain write access to the resource. When one non-ISR thread has write
    access, all read and write accesses by other non-ISR threads must wait until the write-access holder
    releases the lock. However, if a non-ISR thread has read access, other non-ISR threads can concurrently
    acquire read access.

Initialize and use this type of lock for resources that are frequently accessed for reading and
    infrequently accessed for writing.

Once resource access is complete, the driver calls the 
    <a href="netvista.ndisreleasereadwritelock">
    NdisReleaseReadWriteLock</a> function.

Each lock that a driver initializes does one of the following:

Protects a discrete set of shared resources from simultaneous write and read access by driver
      threads that run at IRQL &lt;= DISPATCH_LEVEL.

Exposes a discrete set of shared resources to simultaneous read access by driver threads that run at
      IRQL &lt;= DISPATCH_LEVEL.

Callers of 
    <b>NdisInitializeReadWriteLock</b> can run at any IRQL. Usually a caller is running at IRQL =
    PASSIVE_LEVEL during initialization.


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
Deprecated for NDIS 6.20 and later drivers, which should use <a href="netvista.ndisallocaterwlock">NdisAllocateRWLock</a> instead of <b>NdisInitializeReadWriteLock</b>. Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/e1054867-51c5-4181-a775-b74cfc69ffcc">NdisInitializeReadWriteLock
   (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisInitializeReadWriteLock
   (NDIS 5.1)</b>) in Windows XP.

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
DLL

</th>
<td width="70%">
<dl>
<dt>Ndis.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level (see Remarks section)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndisacquirereadwritelock">NdisAcquireReadWriteLock</a>
</dt>
<dt>
<a href="netvista.ndisreleasereadwritelock">NdisReleaseReadWriteLock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInitializeReadWriteLock function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

