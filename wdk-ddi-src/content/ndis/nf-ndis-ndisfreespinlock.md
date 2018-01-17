---
UID: NF:ndis.NdisFreeSpinLock
title: NdisFreeSpinLock function
author: windows-driver-content
description: The NdisFreeSpinLock function releases a spin lock initialized in a preceding call to the NdisAllocateSpinLock functioin.
old-location: netvista\ndisfreespinlock.htm
old-project: netvista
ms.assetid: 4807d413-c40f-4ee8-b670-9afcac809bd2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisFreeSpinLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisFreeSpinLock (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisFreeSpinLock (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisFreeSpinLock
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
req.irql: Any level (see Remarks section)
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisFreeSpinLock function



## -description
The 
  <b>NdisFreeSpinLock</b> function releases a spin lock initialized in a preceding call to the 
  <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> functioin.



## -syntax

````
VOID NdisFreeSpinLock(
  _In_ PNDIS_SPIN_LOCK SpinLock
);
````


## -parameters

### -param SpinLock [in]

Pointer to the spin lock to be deinitialized.


## -returns
None


## -remarks
If the caller of 
    <b>NdisFreeSpinLock</b> needs to use the spin lock again, it must call 
    <b>NdisAllocateSpinLock</b> before passing that spin lock pointer to any of the 
    <b>Ndis..SpinLock</b> or 
    <b>NdisInterlocked<i>Xxx</i></b> functions.

Callers of 
    <b>NdisFreeSpinLock</b> can run at any IRQL. Usually, this function is not called until a driver is
    unloading.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisacquirespinlock.md">NdisAcquireSpinLock</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisdpracquirespinlock.md">NdisDprAcquireSpinLock</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisdprreleasespinlock.md">NdisDprReleaseSpinLock</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisinterlockedaddulong.md">NdisInterlockedAddUlong</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisinterlockedinsertheadlist.md">
   NdisInterlockedInsertHeadList</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisinterlockedinserttaillist.md">
   NdisInterlockedInsertTailList</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisinterlockedremoveheadlist.md">
   NdisInterlockedRemoveHeadList</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeSpinLock function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

