---
UID: NF.ndis.NdisMAllocateSharedMemoryAsyncEx
title: NdisMAllocateSharedMemoryAsyncEx function
author: windows-driver-content
description: Miniport drivers call the NdisMAllocateSharedMemoryAsyncEx function to allocate additional memory shared between the driver and its bus-master DMA NIC, usually when the miniport driver is running low on available NIC receive buffers.
old-location: netvista\ndismallocatesharedmemoryasyncex.htm
old-project: NetVista
ms.assetid: ccbe98ca-7da9-4159-ac1a-c25ec6745ff4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisMAllocateSharedMemoryAsyncEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMAllocateSharedMemoryAsyncEx
req.alt-loc: ndis.h
req.ddi-compliance: Irql_Gather_DMA_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisMAllocateSharedMemoryAsyncEx function



## -description
Miniport drivers call the 
  <b>NdisMAllocateSharedMemoryAsyncEx</b> function to allocate additional memory shared between the driver and
  its bus-master DMA NIC, usually when the miniport driver is running low on available NIC receive
  buffers.



## -syntax

````
NDIS_STATUS NdisMAllocateSharedMemoryAsyncEx(
  _In_ NDIS_HANDLE MiniportDmaHandle,
  _In_ ULONG       Length,
  _In_ BOOLEAN     Cached,
  _In_ PVOID       Context
);
````


## -parameters

### -param MiniportDmaHandle [in]

A handle to a context area that NDIS uses to manage a DMA resource. The caller obtained this
     handle by calling the 
     <a href="netvista.ndismregisterscattergatherdma">
     NdisMRegisterScatterGatherDma</a> function.


### -param Length [in]

The number of bytes to allocate.


### -param Cached [in]

This parameter is ignored (cached memory is always used on x86 and x64 systems).


### -param Context [in]

A pointer to driver-determined context to be passed to the 
     <a href="..\ndis\nc-ndis-miniport_allocate_shared_mem_complete.md">MiniportSharedMemoryAllocateComplete</a> function when it is called.


## -returns
<b>NdisMAllocateSharedMemoryAsyncEx</b> can return one of the following:
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>NDIS will call the 
       <a href="..\ndis\nc-ndis-miniport_allocate_shared_mem_complete.md">MiniportSharedMemoryAllocateComplete</a> function and provide information that describes the
       allocated shared memory. If the attempt to allocate shared memory fails, NDIS calls 
       <i>MiniportSharedMemoryAllocateComplete</i> and passes <b>NULL</b> pointers.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>The requested memory could not be allocated at this time. If 
       <a href="netvista.ndismallocatesharedmemoryasyncex">NdisMAllocateSharedMemoryAsyncEx</a> returns this status, a subsequent call with the same parameters
       might succeed, depending on whether system resources have become available.

 


## -remarks
Drivers of bus-master DMA NICs call 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> to dynamically allocate shared memory. Such drivers also allocate
    shared memory space during initialization. These drivers use the dynamically allocated shared memory for
    transfer operations when high network traffic places excessive demands on the existing shared memory
    space.

Such a miniport driver usually maintains one or more state variables to track the number of shared
    memory buffers available for incoming transfers. When the number of available buffers reaches a
    driver-determined low, the miniport driver calls 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> to allocate more buffer space in shared memory. When the number of
    available buffers climbs to a driver-determined high, the miniport driver calls 
    <a href="netvista.ndismfreesharedmemory">NdisMFreeSharedMemory</a> one or more
    times to release its preceding dynamic allocations.

Usually, such a miniport driver retains the block of shared memory that its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function
    allocated with 
    <a href="netvista.ndismallocatesharedmemory">NdisMAllocateSharedMemory</a> until
    a NIC is removed. When the NIC is removed, NDIS calls the miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function. This allocation
    is sufficient to handle an average demand for transfers through the NIC.

A miniport driver should set a limit on how much shared memory it can allocate. This limit is
    driver-specific and should be high enough so that the driver does not run out of buffers. Do not et a
    limit that is excessively high, as this could result in a wasteful consumption of shared memory that
    could reduce system performance.

Any miniport driver that calls 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> or 
    <a href="netvista.ndismallocatesharedmemory">NdisMAllocateSharedMemory</a> must release all outstanding allocations with one or more calls to 
    <a href="netvista.ndismfreesharedmemory">NdisMFreeSharedMemory</a> when its NIC is removed.


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
Supported in NDIS 6.0 and later.

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
<a href="devtest.ndis_irql_gather_dma_function">Irql_Gather_DMA_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_allocate_shared_mem_complete.md">
   MiniportSharedMemoryAllocateComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="netvista.ndismallocatesharedmemory">NdisMAllocateSharedMemory</a>
</dt>
<dt>
<a href="netvista.ndismfreesharedmemory">NdisMFreeSharedMemory</a>
</dt>
<dt>
<a href="netvista.ndismregisterdmachannel">NdisMRegisterDmaChannel</a>
</dt>
<dt>
<a href="netvista.ndismregisterscattergatherdma">
   NdisMRegisterScatterGatherDma</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisMAllocateSharedMemoryAsyncEx function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

