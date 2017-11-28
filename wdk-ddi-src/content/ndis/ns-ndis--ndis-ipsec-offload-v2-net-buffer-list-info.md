---
UID: NS.ndis._NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO
title: NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO
author: windows-driver-content
description: The NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure specifies information that is used in offloading Internet protocol security offload version 2 (IPsecOV2) tasks from the TCP/IP transport to a NIC.
old-location: netvista\ndis_ipsec_offload_v2_net_buffer_list_info.htm
old-project: netvista
ms.assetid: f528ae2f-54fc-4edc-99bf-b1958837584b
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO
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
req.irql: See Remarks section
req.iface: 
---

# NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure



## -description
<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]</p>
<p>The <b>NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</b> structure specifies information that is used in
  offloading Internet protocol security offload version 2 (IPsecOV2) tasks from the TCP/IP transport to a
  NIC.</p>


## -syntax

````
typedef struct _NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO {
  union {
    struct {
      PVOID OffloadHandle;
    } Transmit;
    struct {
      ULONG SaDeleteReq  :1;
      ULONG CryptoDone  :1;
      ULONG NextCryptoDone  :1;
      ULONG Reserved  :13;
      ULONG CryptoStatus  :16;
    } Receive;
  };
} NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO;
````


## -struct-fields
<dl>

### -field <b>Transmit</b>

<dd>
<p>A structure that contains the following members:</p>
<dl>

### -field <b>OffloadHandle</b>

<dd>
<p>A handle to the outbound security association (SA) for a packet that has just one IPsec payload
       for a transport (end-to-end) connection.</p>
</dd>
</dl>
</dd>

### -field <b>Receive</b>

<dd>
<p>A structure that contains the following members:</p>
<dl>

### -field <b>SaDeleteReq</b>

<dd>
<p>A ULONG value that, when set, indicates that the TCP/IP transport should issue the 
       <a href="netvista.oid_tcp_task_ipsec_offload_v2_delete_sa">
       OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</a> OID once to delete the inbound SA that the packet was
       received over and once again to delete the outbound SA that corresponds to the deleted inbound SA. The
       network interface card (NIC) must not remove either of these SAs before it receives the corresponding
       OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA request.</p>
</dd>

### -field <b>CryptoDone</b>

<dd>
<p>A ULONG value that, when set, indicates that a NIC performed IPsec checking on at least one
       IPsec payload in the receive packet. When this value is cleared, it indicates that the NIC did not
       perform IPsec checking on the packet.</p>
</dd>

### -field <b>NextCryptoDone</b>

<dd>
<p>A ULONG value that, when set, indicates that a NIC performed IPsec checking on both the tunnel
       and transport portions of the receive packet. 
       <b>CryptoDone</b> must also be set in this case. 
       <b>NextCryptoDone</b> is set only if a packet has both tunnel and transport IPsec payloads; otherwise, 
       <b>NextCryptoDone</b> is set to zero.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved for NDIS.</p>
</dd>

### -field <b>CryptoStatus</b>

<dd>
<p>The result of IPsec checking that a NIC performed on a receive packet. This result can be
       described as one of the following values:
       </p>
<p></p>
<dl>

### -field <a id="CRYPTO_SUCCESS"></a><a id="crypto_success"></a><b>CRYPTO_SUCCESS</b>

<dd>
<p>The packet was successfully decrypted, if necessary, and the authentication header (AH)
         checksums, encapsulating security payload (ESP) checksums, or both checksums in the packet were
         validated.</p>
</dd>

### -field <a id="CRYPTO_GENERIC_ERROR"></a><a id="crypto_generic_error"></a><b>CRYPTO_GENERIC_ERROR</b>

<dd>
<p>The packet failed the IPsec check for an unspecified reason.</p>
</dd>

### -field <a id="CRYPTO_TRANSPORT_AH_AUTH_FAILED"></a><a id="crypto_transport_ah_auth_failed"></a><b>CRYPTO_TRANSPORT_AH_AUTH_FAILED</b>

<dd>
<p>The AH checksum for the transport portion of the packet was invalid.</p>
</dd>

### -field <a id="CRYPTO_TRANSPORT_ESP_AUTH_FAILED"></a><a id="crypto_transport_esp_auth_failed"></a><b>CRYPTO_TRANSPORT_ESP_AUTH_FAILED</b>

<dd>
<p>The ESP checksum for the transport portion of the packet was invalid.</p>
</dd>

### -field <a id="CRYPTO_TUNNEL_AH_AUTH_FAILED"></a><a id="crypto_tunnel_ah_auth_failed"></a><b>CRYPTO_TUNNEL_AH_AUTH_FAILED</b>

<dd>
<p>The AH checksum for the tunnel portion of the packet was invalid.</p>
</dd>

### -field <a id="CRYPTO_TUNNEL_ESP_AUTH_FAILED"></a><a id="crypto_tunnel_esp_auth_failed"></a><b>CRYPTO_TUNNEL_ESP_AUTH_FAILED</b>

<dd>
<p>The ESP checksum for the tunnel portion of the packet was invalid.</p>
</dd>

### -field <a id="CRYPTO_INVALID_PACKET_SYNTAX"></a><a id="crypto_invalid_packet_syntax"></a><b>CRYPTO_INVALID_PACKET_SYNTAX</b>

<dd>
<p>The receive packet's length is invalid. For example, the total length in the IP header is not
         sufficient to include all of the fields and headers for AH/ESP.</p>
</dd>

### -field <a id="CRYPTO_INVALID_PROTOCOL"></a><a id="crypto_invalid_protocol"></a><b>CRYPTO_INVALID_PROTOCOL</b>

<dd>
<p>The IPsec protocols that were specified in the SA that the packet was received on do not match
         the IPsec protocols that were found in the packet. For example, this error occurs if the SA that the
         packet was received on specifies the AH protocol but the packet contained only an ESP header.</p>
</dd>
</dl>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>Before the TCP/IP transport passes an outbound packet to a NIC for offload processing, the transport
    specifies the IPsec information in the NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure that is
    associated with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.</p>

<p>Specifically, the TCP/IP transport supplies a value for the 
    <b>OffloadHandle</b> member in the NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure. The 
    <b>OffloadHandle</b> value specifies the handle to the outbound SA for a packet that has just one IPsec
    payload, regardless of whether that payload is for a transport or a tunnel SA. The 
    <b>OffloadHandle</b> value that is supplied in the NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure
    has the same value as the 
    <b>OffloadHandle</b> value that was reported to the TCP/IP transport when the miniport driver successfully
    added a set of SAs to a NIC. All the SAs were added to the NIC when the miniport driver responded to an 
    <a href="netvista.oid_tcp_task_ipsec_offload_v2_add_sa">
    OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a> request.</p>

<p>Before a miniport driver indicates up a receive packet that has one or more IPsec payloads, the driver
    specifies IPsec information in the NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure that is
    associated with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.</p>

<p>To set and get the IPsec information, use the 
    <b>IPsecOffloadV2NetBufferListInfo</b> index with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro.
    NET_BUFFER_LIST_INFO returns the NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.1 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565801">NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>
</dt>
<dt>
<a href="netvista.oid_tcp_task_ipsec_offload_v2_add_sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a>
</dt>
<dt>
<a href="netvista.oid_tcp_task_ipsec_offload_v2_delete_sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
