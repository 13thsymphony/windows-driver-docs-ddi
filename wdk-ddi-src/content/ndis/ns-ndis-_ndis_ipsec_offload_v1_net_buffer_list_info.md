---
UID: NS:ndis._NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
title: _NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
author: windows-driver-content
description: The NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO structure specifies information that is used in offloading Internet protocol security (IPsec) tasks from the TCP/IP transport to a miniport driver.
old-location: netvista\ndis_ipsec_offload_v1_net_buffer_list_info.htm
old-project: netvista
ms.assetid: 990b3df6-5ef7-4201-a09d-d94822d0a8bb
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0. For NDIS 6.1 and later, use NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
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
req.typenames: *PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
---

# _NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO structure



## -description
The <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure specifies information that is used in
  offloading Internet protocol security (IPsec) tasks from the TCP/IP transport to a miniport driver.



## -syntax

````
typedef struct _NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO {
  union {
    struct {
      NDIS_HANDLE OffloadHandle;
    } Transmit;
    struct {
      USHORT SaDeleteReq  :1;
      USHORT CryptoDone  :1;
      USHORT NextCryptoDone  :1;
      USHORT Pad  :13;
      USHORT CryptoStatus;
    } Receive;
  };
} NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO;
````


## -struct-fields

### -field Transmit

A structure that contains the following members:


### -field OffloadHandle

A handle to the outbound security association (SA) for a packet that has just one IPsec payload,
       regardless of whether that payload is for a transport (end-to-end) connection or a tunnel
       connection.

</dd>
</dl>

### -field Receive

A structure that contains the following members:


### -field SaDeleteReq

A USHORT value that, when set, indicates that the TCP/IP transport should issue the 
       <a href="netvista.oid_tcp_task_ipsec_delete_sa">
       OID_TCP_TASK_IPSEC_DELETE_SA</a> OID once to delete the inbound SA that the packet was received over
       and once again to delete the outbound SA that corresponds to the deleted inbound SA. The network
       interface card (NIC) must not remove either of these SAs before it receives the corresponding
       OID_TCP_TASK_IPSEC_DELETE_SA request.


### -field CryptoDone

A USHORT value that, when set, indicates that a NIC performed IPsec checking on at least one
       IPsec payload in the receive packet. When this value is cleared, it indicates that the NIC did not
       perform IPsec checking on the packet.


### -field NextCryptoDone

A USHORT value that, when set, indicates that a NIC performed IPsec checking on both the tunnel
       and transport portions of the receive packet. 
       <b>CryptoDone</b> must also be set in this case. 
       <b>NextCryptoDone</b> is set only if a packet has both tunnel and transport IPsec payloads; otherwise, 
       <b>NextCryptoDone</b> is set to zero.


### -field Pad

Reserved for NDIS.


### -field CryptoStatus

The result of IPsec checking that a NIC performed on a receive packet. This result can be
       described as one of the following values:
       

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field 
          CRYPTO_SUCCESS</b>
</dl>
</td>
<td width="60%">
The packet was successfully decrypted, if necessary, and the authentication header (AH)
         checksums, encapsulating security payload (ESP) checksums, or both checksums in the packet were
         validated.

</td>
</tr>
<tr>

### -field 
          CRYPTO_GENERIC_ERROR</b>
</dl>
</td>
<td width="60%">
The packet failed the IPsec check for an unspecified reason.

</td>
</tr>
<tr>

### -field 
          CRYPTO_TRANSPORT_AH_AUTH_FAILED</b>
</dl>
</td>
<td width="60%">
The AH checksum for the transport portion of the packet was invalid.

</td>
</tr>
<tr>

### -field 
          CRYPTO_TRANSPORT_ESP_AUTH_FAILED</b>
</dl>
</td>
<td width="60%">
The ESP checksum for the transport portion of the packet was invalid.

</td>
</tr>
<tr>

### -field 
          CRYPTO_TUNNEL_AH_AUTH_FAILED</b>
</dl>
</td>
<td width="60%">
The AH checksum for the tunnel portion of the packet was invalid.

</td>
</tr>
<tr>

### -field 
          CRYPTO_TUNNEL_ESP_AUTH_FAILED</b>
</dl>
</td>
<td width="60%">
The ESP checksum for the tunnel portion of the packet was invalid.

</td>
</tr>
<tr>

### -field 
          CRYPTO_INVALID_PACKET_SYNTAX</b>
</dl>
</td>
<td width="60%">
The receive packet's length is invalid.

</td>
</tr>
<tr>

### -field 
          CRYPTO_INVALID_PROTOCOL</b>
</dl>
</td>
<td width="60%">
The IPsec protocols that were specified in the SA that the packet was received on do not match
         the IPsec protocols that were found in the packet. For example, this error occurs if the SA that the
         packet was received on specifies the AH protocol but the packet contained only an ESP header.

</td>
</tr>
</table>
 

</dd>
</dl>

## -remarks
Before the TCP/IP transport passes a send packet that a NIC will perform IPsec tasks on to the
    miniport driver of the NIC, the transport updates the IPsec information in the
    <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure that is associated with the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

Specifically, the TCP/IP transport supplies a value for the 
    <b>OffloadHandle</b> member in the <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure. The 
    <b>OffloadHandle</b> value specifies the handle to the outbound security association (SA) for a packet
    that has just one IPsec payload, regardless of whether that payload is for a transport (end-to-end)
    security association or a tunnel security association. The 
    <b>OffloadHandle</b> value that is supplied in the <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure
    has the same value as the 
    <b>OffloadHandle</b> value that the TCP/IP transport supplied when it set 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a> to request
    the miniport driver to add the outbound SA to the NIC.

Before a miniport driver indicates up a receive packet that has one or more IPsec payloads, the driver
    updates the <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure that is associated with the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure as follows:

If the NIC performed IPsec checks on at least one IPsec payload in the packet, the miniport driver
      sets the 
      <b>CryptoDone</b> member and indicates the results of the checksum validation tests by specifying the
      appropriate value in the 
      <b>CryptoStatus</b> member.

If the NIC performed IPsec checking on both the tunnel and transport portions of a receive packet,
      the miniport driver also sets the 
      <b>NextCryptoDone</b> member. 
      <b>NextCryptoDone</b> is set only if a packet has both tunnel and transport IPsec payloads; otherwise, 
      <b>NextCryptoDone</b> is set to zero.

If the NIC did not perform IPsec checks on the packet, the miniport driver does not set 
      <b>CryptoDone</b> or 
      <b>NextCryptoDone</b> and does not supply a 
      <b>CryptoStatus</b> value.

To create space for another SA on the NIC, the miniport driver of the NIC can set 
    <b>SaDeleteReq</b> in the <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure for a receive packet. The
    TCP/IP transport subsequently issues 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569810">OID_TCP_TASK_IPSEC_DELETE_SA</a> once
    to delete the inbound SA that the packet was received over and once again to delete the outbound SA that
    corresponds to the deleted inbound SA. The NIC must not remove either of these SAs before receiving the
    corresponding OID_TCP_TASK_IPSEC_DELETE_SA request. The miniport driver of the NIC can set 
    <b>SaDeleteReq</b> independently of 
    <b>CryptoDone</b> .

To set and get the IPsec information, use the 
    <b>IPsecOffloadV1NetBufferListInfo</b> index with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro.
    <b>NET_BUFFER_LIST_INFO</b> returns the <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure.


## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v2_net_buffer_list_info.md">NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569810">OID_TCP_TASK_IPSEC_DELETE_SA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

