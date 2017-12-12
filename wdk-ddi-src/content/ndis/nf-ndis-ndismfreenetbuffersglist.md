---
UID: NF.ndis.NdisMFreeNetBufferSGList
title: NdisMFreeNetBufferSGList function
author: windows-driver-content
description: Bus-master miniport drivers call the NdisMFreeNetBufferSGList function to free scatter/gather list resources that were allocated by calling the NdisMAllocateNetBufferSGList function.
old-location: netvista\ndismfreenetbuffersglist.htm
old-project: netvista
ms.assetid: 22945e04-9feb-4f4b-9ca6-916dab372a64
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisMFreeNetBufferSGList
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
req.alt-api: NdisMFreeNetBufferSGList
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Gather_DMA_Function
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

# NdisMFreeNetBufferSGList function



## -description
Bus-master miniport drivers call the 
  <b>NdisMFreeNetBufferSGList</b> function to free scatter/gather list resources that were allocated by
  calling the 
  <a href="netvista.ndismallocatenetbuffersglist">
  NdisMAllocateNetBufferSGList</a> function.



## -syntax

````
VOID NdisMFreeNetBufferSGList(
  _In_ NDIS_HANDLE          NdisMiniportDmaHandle,
  _In_ PSCATTER_GATHER_LIST pSGL,
  _In_ PNET_BUFFER          NetBuffer
);
````


## -parameters

### -param NdisMiniportDmaHandle [in]

A handle to a context area that NDIS uses to manage a DMA resource. The caller obtained this
     handle by calling the 
     <a href="netvista.ndismregisterscattergatherdma">
     NdisMRegisterScatterGatherDma</a> function.


### -param pSGL [in]

A pointer to a miniport driver scatter/gather list buffer.


### -param NetBuffer [in]

A pointer to the 
     <a href="netvista.net_buffer">NET_BUFFER</a> structure associated with the
     specified scatter/gather list buffer.


## -returns
None


## -remarks
Bus-master miniport drivers must call the 
    <b>NdisMFreeNetBufferSGList</b> function to free a scatter/gather list. A miniport driver typically calls 
    <b>NdisMFreeNetBufferSGList</b> from its 
    <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> function
    while it is handling a send complete interrupt or at any time that the driver no longer requires the
    scatter/gather list. Do not call 
    <b>NdisMFreeNetBufferSGList</b> while the driver or hardware is still accessing the memory that is
    described by the 
    <a href="netvista.net_buffer">NET_BUFFER</a> structure that is associated with the
    scatter/gather list.

Miniport drivers can free the buffer that was specified in the 
    <i>ScatterGatherListBuffer</i> parameter of the 
    <a href="netvista.ndismallocatenetbuffersglist">NdisMAllocateNetBufferSGList</a> function after 
    <b>NdisMFreeNetBufferSGList</b> returns.

Before accessing received data, miniport drivers must call <b>NdisMFreeNetBufferSGList</b> to flush the memory cache.


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
<a href="devtest.ndis_irql_gather_dma_function">Irql_Gather_DMA_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.ndismallocatenetbuffersglist">NdisMAllocateNetBufferSGList</a>
</dt>
<dt>
<a href="netvista.ndismregisterscattergatherdma">
   NdisMRegisterScatterGatherDma</a>
</dt>
<dt>
<a href="netvista.allocating_and_freeing_scatter_gather_lists">Allocating and Freeing Scatter/Gather Lists</a>
</dt>
<dt>
<a href="netvista.scatter_gather_dma2">Miniport Driver Scatter/Gather DMA</a>
</dt>
<dt>
<a href="netvista.ndis_scatter_gather_dma">NDIS Scatter/Gather DMA</a>
</dt>
<dt>
<a href="netvista.registering_and_deregistering_dma_channels">Registering and Deregistering DMA Channels</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMFreeNetBufferSGList function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

