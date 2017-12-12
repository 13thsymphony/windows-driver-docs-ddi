---
UID: NC.ndischimney.NDIS_TCP_OFFLOAD_FORWARD_COMPLETE
title: NDIS_TCP_OFFLOAD_FORWARD_COMPLETE
author: windows-driver-content
description: An offload target calls the NdisTcpOffloadForwardComplete function to complete one or more forward requests that were made to the MiniportTcpOffloadForward function of the offload target.
old-location: netvista\ndistcpoffloadforwardcomplete.htm
old-project: netvista
ms.assetid: 080949ab-8a27-4d13-992e-597210d4882c
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _PD_BUFFER_VIRTUAL_SUBNET_INFO, PD_BUFFER_VIRTUAL_SUBNET_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisTcpOffloadForwardComplete
req.alt-loc: ndischimney.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
---

# NDIS_TCP_OFFLOAD_FORWARD_COMPLETE callback



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisTcpOffloadForwardComplete</b> function to complete one or more forward requests that were made to the
  
  <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">
  MiniportTcpOffloadForward</a> function of the offload target.



## -prototype

````
VOID NdisTcpOffloadForwardComplete(
  _In_ NDIS_HANDLE      NdisMiniportHandle,
  _In_ PNET_BUFFER_LIST NetBufferList
);
````


## -parameters

### -param NdisMiniportHandle [in]

The handle that the offload target obtained in a previous call to the 
     <a href="netvista.ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> function.


### -param NetBufferList [in]

A pointer to a 
     <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure. This structure
     can be stand-alone or the first structure in a linked list of NET_BUFFER_LIST structures. The offload
     target obtained these structures in one or more calls to its 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">
     MiniportTcpOffloadForward</a> function.


## -returns
None


## -remarks
To improve system performance, an offload target can create a linked list that contains 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures from multiple
    calls to the 
    <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">
    MiniportTcpOffloadForward</a> function. The offload target can then pass such a linked list in a single
    call to the 
    <b>NdisTcpOffloadForwardComplete</b> function.

An offload target must write one of the following status values to each NET_BUFFER_LIST structure that
    it passes to the 
    <b>NdisTcpOffloadForwardComplete</b> function:



The offload target accepted all the forwarded TCP segments and has processed them.

The offload target will not process the forwarded TCP segments because the specified TCP
      connection is being uploaded. In this case, the host stack queues and processes the TCP
      segments.

The offload target has received an RST segment on the TCP connection. In this case, the host
      stack does not processes the forwarded TCP segments.


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
<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">MiniportTcpOffloadForward</a>
</dt>
<dt>
<a href="netvista.ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_OFFLOAD_FORWARD_COMPLETE callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

