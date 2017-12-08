---
UID: NS.ndischimney._IP_OFFLOAD_STATS
title: IP_OFFLOAD_STATS
author: windows-driver-content
description: The IP_OFFLOAD_STATS structure contains statistics that an offload target supplies in response to a query of OID_IP4_OFFLOAD_STATS or OID_IP6_OFFLOAD_STATS.
old-location: netvista\ip_offload_stats.htm
old-project: netvista
ms.assetid: f40c5734-2546-40c3-a6fb-58f728c3cc5e
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IP_OFFLOAD_STATS, IP_OFFLOAD_STATS, *PIP_OFFLOAD_STATS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IP_OFFLOAD_STATS
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
req.iface: 
---

# IP_OFFLOAD_STATS structure



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]</p>
<p>The IP_OFFLOAD_STATS structure contains statistics that an offload target supplies in response to a
  query of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569758">OID_IP4_OFFLOAD_STATS</a> or 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569759">OID_IP6_OFFLOAD_STATS</a>.</p>


## -syntax

````
typedef struct _IP_OFFLOAD_STATS {
  ULONG64 InReceives;
  ULONG64 InOctets;
  ULONG64 InDelivers;
  ULONG64 OutRequests;
  ULONG64 OutOctets;
  ULONG   InHeaderErrors;
  ULONG   InTruncatedPackets;
  ULONG   InDiscards;
  ULONG   OutDiscards;
  ULONG   OutNoRoutes;
} IP_OFFLOAD_STATS, *PIP_OFFLOAD_STATS;
````


## -struct-fields
<dl>

### -field InReceives

<dd>
<p>The total number of input IP datagrams that have been received from the interface on offloaded TCP
     connections, including IP datagrams received in error. See 
     "ipInReceives" in RFC 2011.</p>
</dd>

### -field InOctets

<dd>
<p>The total number of octets (bytes) in input IP datagrams that have been received from the
     interface on offloaded TCP connections. Octets from datagrams counted in 
     <b>InReceives</b> must be counted here. 
     <b>InOctets</b> must include the number of bytes in the IP header and payload.</p>
</dd>

### -field InDelivers

<dd>
<p>The number of input IP datagrams that were successfully delivered to offloaded TCP connections.
     See 
     "ipInDelivers" in RFC 2011.</p>
</dd>

### -field OutRequests

<dd>
<p>The number of IP datagrams that the offload target supplied to its IP layer in requests for
     transmission on offloaded TCP connections. See 
     "ipOutRequests" in RFC 2011.</p>
</dd>

### -field OutOctets

<dd>
<p>The total number of octets (bytes) in IP datagrams that the offload target supplied to its IP
     layer in requests for transmission on offloaded TCP connections. Octets from datagrams counted in 
     <b>OutRequests</b> must be counted here. 
     <b>OutOctets</b> must include the number of bytes in the IP header and payload.</p>
</dd>

### -field InHeaderErrors

<dd>
<p>The number of input IP datagrams received on offloaded TCP connections that were discarded because
     of errors in their IP headers. Such errors include bad checksums, version number mismatch, other format
     errors, time-to-live exceeded, and errors discovered in processing IPv6 options if the offload target
     supports such options. (An offload target does not process IPv4 options.) This count does not include
     errors resulting from invalid destination addresses. See 
     "ipInHdrErrors" in RFC 2011.</p>
</dd>

### -field InTruncatedPackets

<dd>
<p>The number of input IP datagrams discarded because the datagram frame didn't carry enough data. 
     <b>InTruncatedPackets</b> should only be incremented if the frame contained a valid header but was
     otherwise shorter than required. Frames that are too short to contain a valid header should be counted
     as 
     <b>InHeaderErrors</b> .</p>
</dd>

### -field InDiscards

<dd>
<p>The number of input IP datagrams received on offloaded TCP connections that contained nothing to
     prevent their further processing but that were discarded for run-time reasons, such as a lack of
     available memory or other resources. See 
     "ipInDiscards" in RFC 2011.</p>
</dd>

### -field OutDiscards

<dd>
<p>The number of output IP datagrams that the offload target supplied to its IP layer for which no
     problem was encountered to prevent their transmission but that were discarded for run-time reasons, such
     as a lack of memory or other resources. See 
     "ipOutDiscards" in RFC 2011.</p>
</dd>

### -field OutNoRoutes

<dd>
<p>The number of output IP datagrams that the offload target supplied to its IP layer that were
     discarded because no route (such as an offloaded path state object) could be found to transmit them to
     their destination. See 
     "ipOutNoRoutes" in RFC 2011.</p>
</dd>
</dl>

## -remarks
<p>The statistics in the IP_OFFLOAD_STATS structure pertain only to IP datagrams that the offload target
    has processed on offloaded TCP connections. The offload target must not include counts for IP datagrams
    on non-offloaded connections. The statistics pertain to a single network interface.</p>

<p>If an offload target has multiple network interfaces, it must maintain separate IP offload statistics
    for each network interface. If the offload target supports both IPv4 and IPv6 connections for a network
    interface, it must maintain one set of IPv4 offload statistics counters and another set of IPv6 offload
    statistics counters for that network interface.</p>

<p>If an offload target's TCP chimney capabilities are enabled (see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff558995">NDIS_TASK_OFFLOAD</a>) and if at least one
    neighbor state object has been offloaded to the offload target, the offload target can process a received
    packet that has a corrupted IP header in one of two ways:</p>

<p>The offload target can indicate the packet through the non-offload interface by calling the 
      <a href="..\ndis\nf-ndis-ndismindicatereceivenetbufferlists.md">
      NdisMIndicateReceiveNetBufferLists</a> function. In this case, the offload target must not increment
      the InHeaderErrors counter. This is the recommended approach.</p>

<p>Alternatively, the offload target can drop the corrupted packet 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff558995">NDIS_TASK_OFFLOAD</a> and increment the
      InHeaderErrors counter.</p>

<p>The host stack integrates the statistics returned by an offload target with the statistics that the
    host stack maintains for non-offloaded TCP connections.</p>

<p>Note that the host stack supplies an IP_OFFLOAD_STATS structure when setting OID_IP4_OFFLOAD_STATS or
    OID_IP6_OFFLOAD_STATS. In either case, however, the offload target does not have to examine the values in
    the IP_OFFLOAD_STATS structure. Instead, when OID_IP4_OFFLOAD_STATS is set, the offload target should
    reset all of its IPv4 statistics counters for offloaded TCP connections. When OID_IP6_OFFLOAD_STATS is
    set, the offload target should reset all of its IPv6 statistics counters for offloaded TCP
    connections.</p>

<p>All of the counters that supply the values for the IP_OFFLOAD_STATS structure wrap (restart from zero)
    when incremented beyond their maximum counts.</p>

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
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndismindicatereceivenetbufferlists.md">
   NdisMIndicateReceiveNetBufferLists</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558995">NDIS_TASK_OFFLOAD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569758">OID_IP4_OFFLOAD_STATS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569759">OID_IP6_OFFLOAD_STATS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20IP_OFFLOAD_STATS structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
