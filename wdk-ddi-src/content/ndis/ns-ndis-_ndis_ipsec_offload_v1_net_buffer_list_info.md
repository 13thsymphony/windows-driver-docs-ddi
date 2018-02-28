---
UID: NS:ndis._NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
title: "_NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO"
author: windows-driver-content
description: The NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO structure specifies information that is used in offloading Internet protocol security (IPsec) tasks from the TCP/IP transport to a miniport driver.
old-location: netvista\ndis_ipsec_offload_v1_net_buffer_list_info.htm
old-project: netvista
ms.assetid: 990b3df6-5ef7-4201-a09d-d94822d0a8bb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, CRYPTO_GENERIC_ERROR, CRYPTO_INVALID_PACKET_SYNTAX, CRYPTO_INVALID_PROTOCOL, CRYPTO_SUCCESS, CRYPTO_TRANSPORT_AH_AUTH_FAILED, CRYPTO_TRANSPORT_ESP_AUTH_FAILED, CRYPTO_TUNNEL_AH_AUTH_FAILED, CRYPTO_TUNNEL_ESP_AUTH_FAILED, NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, ndis/NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, ndis/PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, netvista.ndis_ipsec_offload_v1_net_buffer_list_info, tcpip_offload_ref_2e052bb5-6546-47a9-b51b-f1f77116835d.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
---

# _NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO structure
The <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure specifies information that is used in
  offloading Internet protocol security (IPsec) tasks from the TCP/IP transport to a miniport driver.

## Syntax
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

## Members


## Remarks
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

<ul>
<li>
If the NIC performed IPsec checks on at least one IPsec payload in the packet, the miniport driver
      sets the 
      <b>CryptoDone</b> member and indicates the results of the checksum validation tests by specifying the
      appropriate value in the 
      <b>CryptoStatus</b> member.

</li>
<li>
If the NIC performed IPsec checking on both the tunnel and transport portions of a receive packet,
      the miniport driver also sets the 
      <b>NextCryptoDone</b> member. 
      <b>NextCryptoDone</b> is set only if a packet has both tunnel and transport IPsec payloads; otherwise, 
      <b>NextCryptoDone</b> is set to zero.

</li>
<li>
If the NIC did not perform IPsec checks on the packet, the miniport driver does not set 
      <b>CryptoDone</b> or 
      <b>NextCryptoDone</b> and does not supply a 
      <b>CryptoStatus</b> value.

</li>
</ul>
To create space for another SA on the NIC, the miniport driver of the NIC can set 
    <b>SaDeleteReq</b> in the <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure for a receive packet. The
    TCP/IP transport subsequently issues 
    <a href="https://msdn.microsoft.com/en-us/library/gg155485.aspx">OID_TCP_TASK_IPSEC_DELETE_SA</a> once
    to delete the inbound SA that the packet was received over and once again to delete the outbound SA that
    corresponds to the deleted inbound SA. The NIC must not remove either of these SAs before receiving the
    corresponding OID_TCP_TASK_IPSEC_DELETE_SA request. The miniport driver of the NIC can set 
    <b>SaDeleteReq</b> independently of 
    <b>CryptoDone</b> .

To set and get the IPsec information, use the 
    <b>IPsecOffloadV1NetBufferListInfo</b> index with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro.
    <b>NET_BUFFER_LIST_INFO</b> returns the <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0. For NDIS 6.1 and later, use NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO. Supported in NDIS 6.0. For NDIS 6.1 and later, use NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/gg155485.aspx">OID_TCP_TASK_IPSEC_DELETE_SA</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a>



<a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v2_net_buffer_list_info.md">NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>