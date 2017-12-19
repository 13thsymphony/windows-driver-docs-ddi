---
UID: NF.ndis.NdisInterlockedRemoveHeadList
title: NdisInterlockedRemoveHeadList macro
author: windows-driver-content
description: The NdisInterlockedRemoveHeadList function removes an entry, usually a packet, from the head of a doubly linked list so that access to the list is synchronized in a multiprocessor-safe way.
old-location: netvista\ndisinterlockedremoveheadlist.htm
old-project: NetVista
ms.assetid: 85cbc158-7132-4666-8161-a78251a62e4d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisInterlockedRemoveHeadList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisInterlockedRemoveHeadList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisInterlockedRemoveHeadList (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisInterlockedRemoveHeadList
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
---

# NdisInterlockedRemoveHeadList macro



## -description
The 
  <b>NdisInterlockedRemoveHeadList</b> function removes an entry, usually a packet, from the head of a doubly
  linked list so that access to the list is synchronized in a multiprocessor-safe way.



## -syntax

````
PLIST_ENTRY NdisInterlockedRemoveHeadList(
  [in] PLIST_ENTRY     ListHead,
  [in] PNDIS_SPIN_LOCK SpinLock
);
````


## -parameters

### -param ListHead [in]

A pointer to the head of the doubly linked list from which an entry is to be removed.


### -param SpinLock [in]

A pointer to a caller-supplied spin lock, used to synchronize access to the list.


## -remarks
Before calling any 
    <b>NdisInterlocked..List</b> function, a driver must initialize the variable at 
    <i>ListHead</i> with the 
    <a href="netvista.ndisinitializelisthead">NdisInitializeListHead</a> function and
    the variable at 
    <i>SpinLock</i> with the 
    <a href="netvista.ndisallocatespinlock">NdisAllocateSpinLock</a> function. The
    driver also must provide resident storage for these variables and for its internal queue.

Before calling 
    <b>NdisInterlockedRemoveHeadList</b>, entries are queued with one or more calls to the 
    <b>NdisInterlockedInsert..List</b> functions.

The caller-supplied spin lock prevents any other function from accessing the driver's internal queue
    while 
    <b>NdisInterlockedRemoveHeadList</b> is removing an entry, even when the driver is running on a
    multiprocessor computer.

<b>NdisInterlockedRemoveHeadList</b> raises the IRQL to DISPATCH_LEVEL when it acquires the given spin
    lock and restores the original IRQL before it returns control. Consequently, any driver function that
    calls 
    <b>NdisInterlockedRemoveHeadList</b> cannot be pageable code.

To convert a returned value back to the address of the inserted entry, a driver can use the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a> macro.

If 
    <b>NdisInterlockedRemoveHeadList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for the 
    <i>ListHead</i> parameter must be resident.


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
   <a href="https://msdn.microsoft.com/c43225c8-b3cd-4b7e-a3ce-0c01638e210c">
   NdisInterlockedRemoveHeadList (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>
   NdisInterlockedRemoveHeadList (NDIS 5.1)</b>) in Windows XP.

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
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a>
</dt>
<dt>
<a href="netvista.ndisallocatespinlock">NdisAllocateSpinLock</a>
</dt>
<dt>
<a href="netvista.ndisinitializelisthead">NdisInitializeListHead</a>
</dt>
<dt>
<a href="netvista.ndisinterlockedinsertheadlist">
   NdisInterlockedInsertHeadList</a>
</dt>
<dt>
<a href="netvista.ndisinterlockedinserttaillist">
   NdisInterlockedInsertTailList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisInterlockedRemoveHeadList macro%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
