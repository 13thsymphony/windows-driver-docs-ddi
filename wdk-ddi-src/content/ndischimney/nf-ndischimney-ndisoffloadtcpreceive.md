---
UID: NF.ndischimney.NdisOffloadTcpReceive
title: NdisOffloadTcpReceive function
author: windows-driver-content
description: A protocol driver or an intermediate driver calls the NdisOffloadTcpReceive function to post receive requests (receive buffers) on an offloaded TCP connection.
old-location: netvista\ndisoffloadtcpreceive.htm
old-project: NetVista
ms.assetid: 021f41c4-6ba9-418e-bc18-131ce6d90877
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisOffloadTcpReceive
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisOffloadTcpReceive
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
req.irql: 
---

# NdisOffloadTcpReceive function



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol driver or an intermediate driver calls the 
  <b>NdisOffloadTcpReceive</b> function to post receive requests (receive buffers) on an offloaded TCP
  connection.



## -syntax

````
NDIS_STATUS NdisOffloadTcpReceive(
  _In_ PNDIS_OFFLOAD_HANDLE NdisOffloadHandle,
  _In_ PNET_BUFFER_LIST     NetBufferList
);
````


## -parameters

### -param NdisOffloadHandle [in]

A handle to an 
     <a href="netvista.ndis_offload_handle">NDIS_OFFLOAD_HANDLE</a> structure in the
     caller's context for the offloaded TCP connection. For more information, see 
     <a href="netvista.referencing_offloaded_state_through_an_intermediate_driver">
     Referencing Offloaded State Through an Intermediate Driver</a>.


### -param NetBufferList [in]

A pointer to a 
     <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     Each NET_BUFFER_LIST structure in the list describes one 
     <a href="netvista.net_buffer">NET_BUFFER</a> structure. The NET_BUFFER structure
     points to a chain of memory descriptor lists (MDLs). The NET_BUFFER_LIST and associated structures are
     locked so that they remain resident in physical memory. However, they are not mapped into system
     memory.


## -returns
The 
     <b>NdisOffloadTcpReceive</b> function always returns NDIS_STATUS_PENDING. The receive operation is always
     completed asynchronously.


## -remarks
In response to a call to its 
    <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">
    MiniportTcpOffloadReceive</a> function, an intermediate driver calls the 
    <b>NdisOffloadTcpReceive</b> function to propagate the receive operation to the underlying intermediate
    driver or offload target. For more information, see 
    <a href="netvista.propagating_i_o_operations">Propagating I/O Operations</a>.

To the 
    <b>NdisOffloadTcpReceive</b> function, the intermediate driver passes the following:

An 
      <i>NdisOffloadHandle</i> function that references the NDIS_OFFLOAD_HANDLE structure stored in the
      intermediate driver's context for the offloaded TCP connection. For more information, see 
      <a href="netvista.referencing_offloaded_state_through_an_intermediate_driver">
      Referencing Offloaded State Through an Intermediate Driver</a>.

The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>MiniportTcpOffloadReceive</i> function.

When the underlying driver or offload target subsequently completes the receive operation by calling
    the 
    <b>NdisTcpOffloadReceiveComplete</b> function, NDIS calls the intermediate driver's 
    <i>ProtocolOffloadReceiveComplete</i> function. The intermediate driver then calls the 
    <b>NdisTcpOffloadReceiveComplete</b> function to propagate the completion of the forward operation.


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
Header

</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">MiniportTcpOffloadReceive</a>
</dt>
<dt>
<a href="netvista.ndis_offload_handle">NDIS_OFFLOAD_HANDLE</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_complete.md">
   NdisTcpOffloadReceiveComplete</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-tcp_offload_recv_complete_handler.md">
   ProtocolTcpOffloadReceiveComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisOffloadTcpReceive function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

