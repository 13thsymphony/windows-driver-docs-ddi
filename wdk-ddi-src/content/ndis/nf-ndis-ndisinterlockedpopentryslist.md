---
UID : NF:ndis.NdisInterlockedPopEntrySList
title : NdisInterlockedPopEntrySList macro
author : windows-driver-content
description : The NdisInterlockedPopEntrySList function removes the first entry from a sequenced, singly linked list.
old-location : netvista\ndisinterlockedpopentryslist.htm
old-project : netvista
ms.assetid : 22f79bc7-49e1-43ba-8dff-8847b9a9bcca
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisInterlockedPopEntrySList, NdisInterlockedPopEntrySList macro [Network Drivers Starting with Windows Vista], ndis_interlocked_ref_5e66ef00-4498-4599-be50-f21ef676d032.xml, ndis/NdisInterlockedPopEntrySList, netvista.ndisinterlockedpopentryslist
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInterlockedPopEntrySList   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInterlockedPopEntrySList   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : ndis.h
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisInterlockedPopEntrySList function
The
  <b>NdisInterlockedPopEntrySList</b> function removes the first entry from a sequenced, singly linked
  list.

## Syntax

````
PSINGLE_LIST_ENTRY NdisInterlockedPopEntrySList(
  [in] PSLIST_HEADER   ListHead,
  [in] PNDIS_SPIN_LOCK Lock
);
````

## Parameters

`SListHead`

TBD

`Lock`

A pointer to a caller-supplied spin lock, not currently held by the caller.


## Return Value

None

## Remarks

A driver 
    <u>must not</u> be holding the given 
    <i>Lock</i> when it calls 
    <b>NdisInterlockedPopEntrySList</b>. If necessary, the driver should call the 
    <a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a> function before
    making this call. 
    <b>NdisInterlockedPopEntrySList</b> itself must acquire this spin lock to remove the first entry in the
    S-List, if any, in a multiprocessor-safe way.

The caller must provide resident storage for the 
    <i>Lock</i>, which must be initialized with the 
    <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> function before
    the initial call to any 
    <b>NdisInterlocked..SList</b> function.

If 
    <b>NdisInterlockedPopEntrySList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for the 
    <i>ListHead</i> parameter must be resident.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\ndis\nf-ndis-ndisinitializeslisthead.md">NdisInitializeSListHead</a>

<a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a>

<a href="..\ndis\nf-ndis-ndisquerydepthslist.md">NdisQueryDepthSList</a>

<mshelp:link keywords="netvista.ndisinterlockedpushentryslist" tabindex="0"><b>
   NdisInterlockedPushEntrySList</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndisfreespinlock.md">NdisFreeSpinLock</a>

<a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInterlockedPopEntrySList macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>