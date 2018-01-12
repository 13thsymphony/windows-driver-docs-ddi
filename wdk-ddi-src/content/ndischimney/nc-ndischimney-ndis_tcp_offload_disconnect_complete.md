---
UID: NC:ndischimney.NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE
title: NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE
author: windows-driver-content
description: An offload target calls the NdisTcpOffloadDisconnectComplete function to complete a disconnect request that was initiated by a previous call to the MiniportTcpOffloadDisconnect function of the offload target.
old-location: netvista\ndistcpoffloaddisconnectcomplete.htm
old-project: netvista
ms.assetid: e862d9fe-a60c-4397-95ce-62aa1ef17eae
ms.author: windowsdriverdev
ms.date: 1/8/2018
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
req.alt-api: NdisTcpOffloadDisconnectComplete
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
req.irql: 
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE callback



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisTcpOffloadDisconnectComplete</b> function to complete a disconnect request that was initiated by a
  previous call to the 
  <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_disconnect_handler.md">
  MiniportTcpOffloadDisconnect</a> function of the offload target.



## -prototype

````
VOID NdisTcpOffloadDisconnectComplete(
  _In_ NDIS_HANDLE      NdisMiniportHandle,
  _In_ PNET_BUFFER_LIST NetBufferList
);
````


## -parameters

### -param NdisMiniportHandle [in]

The handle that the offload target obtained in a previous call to the 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a> function.


### -param NetBufferList [in]

A pointer to a single 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. The offload
     target obtained this pointer as an input parameter to its 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_disconnect_handler.md">
     MiniportTcpOffloadDisconnect</a> function.


## -returns
None


## -remarks
<b>Completing an Abortive Disconnect
    </b>

If the offload target issued an abortive disconnect, it must do the following before calling the 
    <b>NdisTcpOffloadDisconnectComplete</b> function:

Complete all outstanding send requests on the connection with a status value of
      NDIS_STATUS_REQUEST_ABORTED. The offload target writes this status value to the 
      <b>Status</b> member of each NET_BUFFER_LIST structure in the linked list that it passes to the 
      <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_send_complete.md">
      NdisTcpOffloadSendComplete</a> function.

Write a status value to the 
      <b>Status</b> member of the NET_BUFFER_LIST structure pointed to by the 
      <i>NetBufferList</i> pointer. A status value of NDIS_STATUS_SUCCESS indicates that the offload target
      successfully sent the RST segment. For a description of the allowable status values, see 
      <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>.

<b>Completing a Graceful Disconnect
    </b>

Before completing a graceful disconnect request, the offload target must:

Write a status value to the 
      <b>Status</b> member of the NET_BUFFER_LIST structure that it passes to the 
      <b>
      NdisTcpOffloadDisconnectComplete</b> function:

Specify the number of user data bytes that were sent and successfully acknowledged. The offload
      target does this by calling the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro with an 
      <i>id</i> of 
      <b>TcpOffloadBytesTransferred</b>.

Call the 
      <a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
      NdisAdvanceNetBufferDataStart</a> function. The 
      <i>NetBufferList</i> parameter should point to the NET_BUFFER structure associated with the
      NET_BUFFER_LIST structure that the offload target passes to the 
      <b>NdisTcpOffloadDisconnectComplete</b> function. The 
      <i>DataOffsetDelta</i> parameter should specify the number of data bytes from the NET_BUFFER structure
      that were both transmitted by the offload target and also successfully acknowledged by the remote host.
      The 
      <i>FreeMdl</i> parameter should be <b>NULL</b>.

Note that the 
    <b>NdisTcpOffloadDisconnectComplete</b> function returns only the NET_BUFFER_LIST structure and associated
    structures that NDIS passed to the offload target's 
    <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_disconnect_handler.md">
    MiniportTcpOffloadDisconnect</a> function. The 
    <b>NdisTcpOffloadDisconnectComplete</b> function cannot return NET_BUFFER_LIST structures that NDIS passed
    in previous calls to the offload target's 
    <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_send_handler.md">
    MiniportTcpOffloadSend</a> function.


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
</table>

## -see-also
<dl>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_disconnect_handler.md">
   MiniportTcpOffloadDisconnect</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
   NdisAdvanceNetBufferDataStart</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_send_complete.md">NdisTcpOffloadSendComplete</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE callback function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

