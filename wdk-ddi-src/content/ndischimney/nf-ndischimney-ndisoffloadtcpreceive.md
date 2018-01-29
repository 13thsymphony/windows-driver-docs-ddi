---
UID : NF:ndischimney.NdisOffloadTcpReceive
title : NdisOffloadTcpReceive function
author : windows-driver-content
description : A protocol driver or an intermediate driver calls the NdisOffloadTcpReceive function to post receive requests (receive buffers) on an offloaded TCP connection.
old-location : netvista\ndisoffloadtcpreceive.htm
old-project : netvista
ms.assetid : 021f41c4-6ba9-418e-bc18-131ce6d90877
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : tcp_chim_ndis_func_601c3cd9-00c3-425b-a42e-c8ea8563bde3.xml, NdisOffloadTcpReceive, ndischimney/NdisOffloadTcpReceive, NdisOffloadTcpReceive function [Network Drivers Starting with Windows Vista], netvista.ndisoffloadtcpreceive
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndischimney.h
req.include-header : Ndischimney.h
req.target-type : Universal
req.target-min-winverclnt : 
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
req.lib : Ndis.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PD_BUFFER_VIRTUAL_SUBNET_INFO
---


# NdisOffloadTcpReceive function
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol driver or an intermediate driver calls the 
  <b>NdisOffloadTcpReceive</b> function to post receive requests (receive buffers) on an offloaded TCP
  connection.

## Syntax

````
NDIS_STATUS NdisOffloadTcpReceive(
  _In_ PNDIS_OFFLOAD_HANDLE NdisOffloadHandle,
  _In_ PNET_BUFFER_LIST     NetBufferList
);
````

## Parameters

`NdisOffloadHandle`

A handle to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_offload_handle.md">NDIS_OFFLOAD_HANDLE</a> structure in the
     caller's context for the offloaded TCP connection. For more information, see 
     <mshelp:link keywords="netvista.referencing_offloaded_state_through_an_intermediate_driver" tabindex="0">
     Referencing Offloaded State Through an Intermediate Driver</mshelp:link>.

`NetBufferList`

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     Each NET_BUFFER_LIST structure in the list describes one 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure. The NET_BUFFER structure
     points to a chain of memory descriptor lists (MDLs). The NET_BUFFER_LIST and associated structures are
     locked so that they remain resident in physical memory. However, they are not mapped into system
     memory.


## Return Value

The 
     <b>NdisOffloadTcpReceive</b> function always returns NDIS_STATUS_PENDING. The receive operation is always
     completed asynchronously.

## Remarks

In response to a call to its 
    <mshelp:link keywords="netvista.miniporttcpoffloadreceive" tabindex="0"><i>
    MiniportTcpOffloadReceive</i></mshelp:link> function, an intermediate driver calls the 
    <b>NdisOffloadTcpReceive</b> function to propagate the receive operation to the underlying intermediate
    driver or offload target. For more information, see 
    <a href="https://msdn.microsoft.com/009159ad-81c0-4555-8e6b-a4fec2c7f1d5">Propagating I/O Operations</a>.

To the 
    <b>NdisOffloadTcpReceive</b> function, the intermediate driver passes the following:
<ul>
<li>
An 
      <i>NdisOffloadHandle</i> function that references the NDIS_OFFLOAD_HANDLE structure stored in the
      intermediate driver's context for the offloaded TCP connection. For more information, see 
      <mshelp:link keywords="netvista.referencing_offloaded_state_through_an_intermediate_driver" tabindex="0">
      Referencing Offloaded State Through an Intermediate Driver</mshelp:link>.

</li>
<li>
The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>MiniportTcpOffloadReceive</i> function.

</li>
</ul>When the underlying driver or offload target subsequently completes the receive operation by calling
    the 
    <b>NdisTcpOffloadReceiveComplete</b> function, NDIS calls the intermediate driver's 
    <i>ProtocolOffloadReceiveComplete</i> function. The intermediate driver then calls the 
    <b>NdisTcpOffloadReceiveComplete</b> function to propagate the completion of the forward operation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndischimney.h (include Ndischimney.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<mshelp:link keywords="netvista.protocoltcpoffloadreceivecomplete" tabindex="0"><i>
   ProtocolTcpOffloadReceiveComplete</i></mshelp:link>

<mshelp:link keywords="netvista.ndistcpoffloadreceivecomplete" tabindex="0"><b>
   NdisTcpOffloadReceiveComplete</b></mshelp:link>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">MiniportTcpOffloadReceive</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\ndischimney\ns-ndischimney-_ndis_offload_handle.md">NDIS_OFFLOAD_HANDLE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisOffloadTcpReceive function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>