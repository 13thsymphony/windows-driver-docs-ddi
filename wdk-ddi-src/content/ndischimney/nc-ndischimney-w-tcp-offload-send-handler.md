---
UID: NC.ndischimney.W_TCP_OFFLOAD_SEND_HANDLER
title: W_TCP_OFFLOAD_SEND_HANDLER
author: windows-driver-content
description: NDIS calls the MiniportTcpOffloadSend function to transmit data on an offloaded TCP connection.
old-location: netvista\miniporttcpoffloadsend.htm
old-project: netvista
ms.assetid: 7c96412f-a866-4863-a06a-9eb6adb2a33b
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: BINARY_DATA, BINARY_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportTcpOffloadSend
req.alt-loc: Ndischimney.h
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
req.iface: 
---

# W_TCP_OFFLOAD_SEND_HANDLER callback



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]</p>
<p>NDIS calls the 
  <i>MiniportTcpOffloadSend</i> function to transmit data on an offloaded TCP connection.</p>


## -prototype

````
W_TCP_OFFLOAD_SEND_HANDLER MiniportTcpOffloadSend;

NDIS_STATUS MiniportTcpOffloadSend(
  _In_ NDIS_HANDLE      MiniportAdapterContext,
  _In_ PVOID            MiniportOffloadContext,
  _In_ PNET_BUFFER_LIST NetBufferList
)
{ ... }
````


## -parameters
<dl>

### -param <i>MiniportAdapterContext</i> [in]

<dd>
<p>The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The offload target provided this handle to NDIS when it
     called 
     <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
     NdisMSetMiniportAttributes</a> from its 
     <a href="..\ndis\nc-ndis-miniport-initialize.md">
     MiniportInitializeEx</a> function.</p>
</dd>

### -param <i>MiniportOffloadContext</i> [in]

<dd>
<p>A pointer to a memory location that contains a PVOID value. This PVOID value references the
     miniport offload context that contains the state object for the TCP connection on which the data is to
     be transmitted. The offload target supplied this PVOID value when it offloaded the TCP connection state
     object.</p>
</dd>

### -param <i>NetBufferList</i> [in]

<dd>
<p>A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     Each NET_BUFFER_LIST structure in the list describes a list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures. Each NET_BUFFER structure
     in the list maps to a chain of memory descriptor lists (MDLs). The MDLs contain the data to be
     transmitted. The NET_BUFFER_LIST and associated structures are locked so that they remain resident in
     physical memory. However, they are not mapped into system memory.</p>
</dd>
</dl>

## -returns
<p>NDIS_STATUS_PENDING is the only return value that is allowed. An offload target always completes a
     send request asynchronously by calling 
     <a href="..\ndischimney\nc-ndischimney-ndis-tcp-offload-send-complete.md">
     NdisTcpOffloadSendComplete</a>.</p>

## -remarks
<p>An offload target must transmit data in first in, first out (FIFO) order. The order of the linked list
    of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that NDIS passes
    at 
    <i>NetBufferList</i> represents the order in which the offload target must transmit the network data. In
    addition, an offload target should send the data that it receives from multiple calls to the 
    <i>MiniportTcpOffloadSend</i> in the order in which the data was posted.</p>

<p>An offload target must accept all send requests made to its 
    <i>MiniportTcpOffloadSend</i> function. If an offload target cannot complete a send request immediately,
    the offload target must queue the request until it can complete it. The offload target should use the 
    <b>MiniportReserved</b> member of a NET_BUFFER_LIST structure to queue send requests. While a send request
    is pending, the offload target retains ownership of the NET_BUFFER_LIST structures and all the resources
    associated with the NET_BUFFER_LIST structures.</p>

<p>The host stack serializes send requests on a per connection basis. The stack will not issue a send
    request on a connection while another send request on that connection is in progress. This ensures that
    the offload target always receives the send requests in the correct order.</p>

<p>Note, however, that the host stack can call the 
    <i>MiniportTcpOffloadSend</i> function on a connection before the offload target has completed one or more
    previous calls to the 
    <i>MiniportTcpOffloadSend</i> function on that same connection. Note also that the host stack can call an
    offload target's 
    <i>MiniportTcpOffloadSend</i> function on one connection while one or more calls to the 
    <i>MiniportTcpOffloadSend</i> function are in progress on another connection.</p>

<p>The 
    <i>MiniportTcpOffloadSend</i> function must synchronize access to its internal queues of network data with
    the offload target's other 
    <i>MiniportXxx</i> functions that access the same queues. An offload target can use spin locks to
    synchronize access to the queues.</p>

<p>The offload target should (but is not required to) set the PSH bit on each NET_BUFFER_LIST boundary.
    The recommended way of doing this is to set the PSH bit in the last segment created from the data
    associated with each NET_BUFFER_LIST structure (that is, the data described by the NET_BUFFER structures
    associated with the NET_BUFFER_LIST structure). Alternatively, the offload target can set the PSH bit in
    the last remaining segment in the send queue before the send queue is emptied.</p>

<p>The host stack will not request the offload target to send urgent data.</p>

<p>An offload target must transmit data in first in, first out (FIFO) order. The order of the linked list
    of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that NDIS passes
    at 
    <i>NetBufferList</i> represents the order in which the offload target must transmit the network data. In
    addition, an offload target should send the data that it receives from multiple calls to the 
    <i>MiniportTcpOffloadSend</i> in the order in which the data was posted.</p>

<p>An offload target must accept all send requests made to its 
    <i>MiniportTcpOffloadSend</i> function. If an offload target cannot complete a send request immediately,
    the offload target must queue the request until it can complete it. The offload target should use the 
    <b>MiniportReserved</b> member of a NET_BUFFER_LIST structure to queue send requests. While a send request
    is pending, the offload target retains ownership of the NET_BUFFER_LIST structures and all the resources
    associated with the NET_BUFFER_LIST structures.</p>

<p>The host stack serializes send requests on a per connection basis. The stack will not issue a send
    request on a connection while another send request on that connection is in progress. This ensures that
    the offload target always receives the send requests in the correct order.</p>

<p>Note, however, that the host stack can call the 
    <i>MiniportTcpOffloadSend</i> function on a connection before the offload target has completed one or more
    previous calls to the 
    <i>MiniportTcpOffloadSend</i> function on that same connection. Note also that the host stack can call an
    offload target's 
    <i>MiniportTcpOffloadSend</i> function on one connection while one or more calls to the 
    <i>MiniportTcpOffloadSend</i> function are in progress on another connection.</p>

<p>The 
    <i>MiniportTcpOffloadSend</i> function must synchronize access to its internal queues of network data with
    the offload target's other 
    <i>MiniportXxx</i> functions that access the same queues. An offload target can use spin locks to
    synchronize access to the queues.</p>

<p>The offload target should (but is not required to) set the PSH bit on each NET_BUFFER_LIST boundary.
    The recommended way of doing this is to set the PSH bit in the last segment created from the data
    associated with each NET_BUFFER_LIST structure (that is, the data described by the NET_BUFFER structures
    associated with the NET_BUFFER_LIST structure). Alternatively, the offload target can set the PSH bit in
    the last remaining segment in the send queue before the send queue is emptied.</p>

<p>The host stack will not request the offload target to send urgent data.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564609">NdisTcpOffloadSendComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20W_TCP_OFFLOAD_SEND_HANDLER callback function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
