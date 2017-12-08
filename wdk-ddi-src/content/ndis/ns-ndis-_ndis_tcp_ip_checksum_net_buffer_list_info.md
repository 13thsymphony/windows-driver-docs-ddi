---
UID: NS.NDIS._NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
title: _NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
author: windows-driver-content
description: The NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO structure specifies information used in offloading checksum tasks from the TCP/IP transport to a NIC.
old-location: netvista\ndis_tcp_ip_checksum_net_buffer_list_info.htm
old-project: netvista
ms.assetid: 989ecf50-18c4-4977-b845-b3fea0cade47
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO, *PNDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO, NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO
req.alt-loc: ndis.h
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

# _NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO structure



## -description
The <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b> structure specifies information used in offloading
  checksum tasks from the TCP/IP transport to a NIC. The <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b> structure
  is part of the 
  <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> information (out-of-band data)
  that is associated with a <b>NET_BUFFER_LIST</b> structure.


## -syntax

````
typedef struct _NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO {
  union {
    struct {
      ULONG IsIPv4  :1;
      ULONG IsIPv6  :1;
      ULONG TcpChecksum  :1;
      ULONG UdpChecksum  :1;
      ULONG IpHeaderChecksum  :1;
      ULONG Reserved  :11;
      ULONG TcpHeaderOffset  :10;
    } Transmit;
    struct {
      ULONG TcpChecksumFailed  :1;
      ULONG UdpChecksumFailed  :1;
      ULONG IpChecksumFailed  :1;
      ULONG TcpChecksumSucceeded  :1;
      ULONG UdpChecksumSucceeded  :1;
      ULONG IpChecksumSucceeded  :1;
      ULONG Loopback  :1;
#if (NDIS_SUPPORT_NDIS630)
      ULONG TcpChecksumValueInvalid  :1;
      ULONG IpChecksumValueInvalid  :1;
#endif 
    } Receive;
    PVOID  Value;
  };
} NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO, *PNDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO;
````


## -struct-fields

### -field Transmit

A structure that contains the following members:

### -field IsIPv4

Set by the TCP/IP transport to indicate that the send packet contains IPv4 addresses.

### -field IsIPv6

Set by the TCP/IP transport to indicate that the send packet contains IPv6 addresses.

### -field TcpChecksum

Set by the TCP/IP transport to indicate that the NIC should calculate the packet's TCP
       checksum.

### -field UdpChecksum

Set by the TCP/IP transport to indicate that the NIC should calculate the packet's UDP
       checksum.

### -field IpHeaderChecksum

Set by the TCP/IP transport to indicate that the NIC should calculate the IP checksum for the
       first IP header in the packet. If the packet contains both a tunnel IP header and a transport IP
       header, the NIC should calculate the checksum for both IP headers.

### -field Reserved

Reserved for NDIS.

### -field TcpHeaderOffset

The offset, in bytes, of the TCP header from the beginning of the packet for TCP packets.
       Miniport drivers can use 
       <b>TcpHeaderOffset</b> to determine the location of the TCP header so that they do not need to parse
       the MAC and IP header.
</dd>
</dl>

### -field Receive

A structure that contains the following members:

### -field TcpChecksumFailed

Set by the miniport driver to indicate that the TCP checksum calculated by the NIC did not match
       the checksum in the receive packet's TCP header.

### -field UdpChecksumFailed

Set by the miniport driver to indicate that the UDP checksum calculated by the NIC did not match
       the checksum in the receive packet's UDP header.

### -field IpChecksumFailed

Set by the miniport driver to indicate that the IP checksum calculated by the NIC did not match
       the checksum in the receive packet's first IP header. If the receive packet contains both a tunnel IP
       header and a transport IP header, the NIC validates the checksum for both IP headers.
<div class="alert"><b>Note</b>  For encapsulated packets that have both a tunnel (outer) IPv4 header and a transport (inner) IPv4 header, the miniport driver should set this flag if either of the IP header checksum validations failed.</div>
<div> </div>

### -field TcpChecksumSucceeded

Set by the miniport driver to indicate that the TCP checksum calculated by the NIC matched the
       checksum in the receive packet's TCP header.

### -field UdpChecksumSucceeded

Set by the miniport driver to indicate that the UDP checksum calculated by the NIC matched the
       checksum in the receive packet's UDP header.

### -field IpChecksumSucceeded

Set by the miniport driver to indicate that the IP checksum calculated by the NIC matched the
       checksum in the receive packet's first IP header. If the receive packet contains both a tunnel IP
       header and a transport IP header, the NIC validates the checksum for the both IP headers.
<div class="alert"><b>Note</b>  For encapsulated packets that have both a tunnel (outer) IPv4 header and a transport (inner) IPv4 header, the miniport driver should set this flag only if both IP header checksum validations succeeded.</div>
<div> </div>

### -field Loopback

NDIS uses this bit. The miniport driver must not examine or set this bit; the miniport driver
       should just ignore this bit.

### -field TcpChecksumValueInvalid

A miniport driver that supports <a href="netvista.receive_segment_coalescing__rsc_">Receive Segment Coalescing (RSC)</a> sets this flag to indicate that the TCP header checksum was validated by the NIC but the TCP header checksum value in the packet is not valid. For more information, see <a href="netvista.indicating_coalesced_segments">Indicating Coalesced Segments</a>.
Miniport drivers that do  not support RSC should set this flag to zero.
<div class="alert"><b>Note</b>  This flag is supported in NDIS 6.30 and later miniport drivers in Windows 8, Windows Server 2012, and later.</div>
<div> </div>

### -field IpChecksumValueInvalid

A miniport driver that supports RSC sets this flag to indicate that for an IPv4 packet, the IP header checksum was validated by the NIC but the IP header checksum value in the packet is not valid. For a packet consisting of both a tunnel and a transport IP header, this bit is applicable only to the tunnel IP header. For more information, see <a href="netvista.indicating_coalesced_segments">Indicating Coalesced Segments</a>.
Miniport drivers that do  not support RSC should set this flag to zero.
<div class="alert"><b>Note</b>  This flag is supported in NDIS 6.30 and later miniport drivers in Windows 8, Windows Server 2012, and later.</div>
<div> </div>
</dd>
</dl>

### -field Value

A <b>PVOID</b> version of the checksum information. Miniport drivers can use this member to access the
      raw information instead of the specific fields.

## -remarks
The <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b> structure specifies information that is used in
    offloading checksum tasks from the TCP/IP transport to a NIC. The
    <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b> structure is part of the 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> information (out-of-band
    data) that is associated with a <b>NET_BUFFER_LIST</b> structure.

Before the TCP/IP transport passes to the miniport driver a TCP/IP packet on which the miniport driver
    will perform checksum tasks, the TCP/IP transport updates the <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b>
    structure that is associated with the <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure. Specifically, the TCP/IP transport sets
    the 
    <b>IsIPv4</b> or 
    <b>IsIPv6</b> flag to indicate that the send packet is an IPv4 or IPv6 packet. If the TCP/IP transport
    does not set either the 
    <b>IsIPv4</b> or 
    <b>IsIPv6</b> flag, the miniport driver should not perform checksum tasks on the packet. If the TCP/IP
    transport sets the 
    <b>IsIPv4</b> or 
    <b>IsIPv6</b> flag, it also sets the 
    <b>IpHeaderChecksum</b>, <b>TcpChecksum</b>, or 
    <b>UdpChecksum</b> flags that are required to indicate which checksums the miniport driver should
    calculate for the packet.

Before indicating up a receive TCP/IP packet on which it performs checksum tasks, a miniport driver
    sets the appropriate 
    Xxx<b>ChecksumFailed</b> or 
    Xxx<b>ChecksumSucceeded</b> flags in the <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b> structure.

To obtain the <b>NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</b> structure, a driver should call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro with an 
    <i>_Id</i> of 
    <b>TcpIpChecksumNetBufferListInfo</b>.

## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>
</dt>
<dt>
<a href="netvista.indicating_coalesced_segments">Indicating Coalesced Segments</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
