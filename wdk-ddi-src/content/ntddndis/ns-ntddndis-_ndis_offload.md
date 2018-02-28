---
UID: NS:ntddndis._NDIS_OFFLOAD
title: "_NDIS_OFFLOAD"
author: windows-driver-content
description: The NDIS_OFFLOAD structure specifies several computational tasks that can be offloaded to the network adapter.
old-location: netvista\ndis_offload.htm
old-project: netvista
ms.assetid: 9d1447f1-aae8-4c27-a27b-e521c0c8ca97
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_OFFLOAD, IPSEC_OFFLOAD_V2_AND_TCP_CHECKSUM_COEXISTENCE, IPSEC_OFFLOAD_V2_AND_UDP_CHECKSUM_COEXISTENCE, NDIS_OFFLOAD, NDIS_OFFLOAD structure [Network Drivers Starting with Windows Vista], PNDIS_OFFLOAD, PNDIS_OFFLOAD structure pointer [Network Drivers Starting with Windows Vista], _NDIS_OFFLOAD, netvista.ndis_offload, ntddndis/NDIS_OFFLOAD, ntddndis/PNDIS_OFFLOAD, tcpip_offload_ref_e5f796e9-714c-43f9-98e4-1d0de0dcc8ee.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista,Supported in NDIS 6.0 and later.
req.target-min-winversvr: Windows Server 2008
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_OFFLOAD
product: Windows
targetos: Windows
req.typenames: NDIS_OFFLOAD, *PNDIS_OFFLOAD
---

# _NDIS_OFFLOAD structure
The NDIS_OFFLOAD structure specifies several computational <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/task-offload">tasks that can be offloaded to the network adapter</a>.

## Syntax
````
typedef struct _NDIS_OFFLOAD {
  NDIS_OBJECT_HEADER                    Header;
  NDIS_TCP_IP_CHECKSUM_OFFLOAD          Checksum;
  NDIS_TCP_LARGE_SEND_OFFLOAD_V1        LsoV1;
  NDIS_IPSEC_OFFLOAD_V1                 IPsecV1;
  NDIS_TCP_LARGE_SEND_OFFLOAD_V2        LsoV2;
  ULONG                                 Flags;
#if (NDIS_SUPPORT_NDIS61)
  NDIS_IPSEC_OFFLOAD_V2                 IPsecV2;
#endif 
#if (NDIS_SUPPORT_NDIS630)
  NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD    Rsc;
  NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD EncapsulatedPacketTaskOffloadGre;
#endif 
} NDIS_OFFLOAD, *PNDIS_OFFLOAD;
````

## Members


`Checksum`

Checksum offload information in an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_tcp_ip_checksum_offload.md">
     NDIS_TCP_IP_CHECKSUM_OFFLOAD</a> structure.

`EncapsulatedPacketTaskOffloadGre`

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/jj991956">Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload</a> information in an <a href="..\ntddndis\ns-ntddndis-_ndis_encapsulated_packet_task_offload.md">NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD</a> structure. This member should only be set by miniport drivers that support task offloads for NVGRE-formatted packets.<div class="alert"><b>Note</b>  This member is available only in NDIS 6.30 and later. </div>
<div> </div>

`EncapsulatedPacketTaskOffloadVxlan`



`EncapsulationTypes`



`Flags`

A bitwise OR  of flags that specify properties that the network adapter supports. The following flags are defined.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="IPSEC_OFFLOAD_V2_AND_TCP_CHECKSUM_COEXISTENCE"></a><a id="ipsec_offload_v2_and_tcp_checksum_coexistence"></a><dl>
<dt><b>IPSEC_OFFLOAD_V2_AND_TCP_CHECKSUM_COEXISTENCE</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
The network adapter supports IPsecV2 and TCP checksums.

</td>
</tr>
<tr>
<td width="40%"><a id="IPSEC_OFFLOAD_V2_AND_UDP_CHECKSUM_COEXISTENCE"></a><a id="ipsec_offload_v2_and_udp_checksum_coexistence"></a><dl>
<dt><b>IPSEC_OFFLOAD_V2_AND_UDP_CHECKSUM_COEXISTENCE</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
The network adapter supports IPsecV2 and UDP checksums.

</td>
</tr>
</table>

`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_OFFLOAD</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_OFFLOAD.
     

Set the <b>Revision</b> and <b>Size</b> members of the <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure as follows:<ul>
<li>For NDIS 6.30 and later drivers:<ul>
<li>Set <b>Revision</b> to NDIS_OFFLOAD_REVISION_3 (NDIS 6.30).</li>
<li>Set <b>Size</b> to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_3.</li>
</ul>
</li>
<li>For NDIS 6.1 and 6.20 drivers:<ul>
<li>Set <b>Revision</b> to NDIS_OFFLOAD_REVISION_2 (NDIS 6.1).</li>
<li>Set <b>Size</b> to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_2.</li>
</ul>
</li>
<li>For NDIS 6.0 drivers:<ul>
<li>Set <b>Revision</b> to NDIS_OFFLOAD_REVISION_1 (NDIS 6.0).</li>
<li>Set <b>Size</b> to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_1.</li>
</ul>
</li>
</ul>

`IPsecV1`

Internet protocol security (IPsec) offload information in an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_ipsec_offload_v1.md">
     NDIS_IPSEC_OFFLOAD_V1</a> structure.

`IPsecV2`

Internet protocol security (IPsec) offload version 2 information in an 
      <a href="..\ntddndis\ns-ntddndis-_ndis_ipsec_offload_v2.md">NDIS_IPSEC_OFFLOAD_V2</a> structure.

`LsoV1`

Large send offload version 1 (LSOV1) information in an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_tcp_large_send_offload_v1.md">
     NDIS_TCP_LARGE_SEND_OFFLOAD_V1</a> structure.

`LsoV2`

Large send offload version 2 (LSOV2) offload information in an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_tcp_large_send_offload_v2.md">
     NDIS_TCP_LARGE_SEND_OFFLOAD_V2</a> structure.

`Rfc6877Xlat`



`Rsc`

<a href="https://msdn.microsoft.com/9CB2AB1C-924C-4A19-B1E7-70C8C5C05B46">Receive Segment Coalescing (RSC)</a> offload information in    an <a href="..\ntddndis\ns-ntddndis-_ndis_tcp_recv_seg_coalesce_offload.md">NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD</a> structure.

## Remarks
The <b>NDIS_OFFLOAD</b> structure is used in the following places:<ul>
<li>The <b>DefaultOffloadConfiguration</b> member of the <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure</li>
<li>The <b>DefaultOffloadConfiguration</b> member of the <a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a> structure</li>
<li>The <b>DefaultOffloadConfiguration</b> member of the <a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a> structure</li>
<li>The <b>InformationBuffer</b> member of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure (which is used in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a> OID request)</li>
<li>The <b>StatusBuffer</b> member of the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567424">NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows Vista,Supported in NDIS 6.0 and later. Windows Vista,Supported in NDIS 6.0 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567424">
   NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/task-offload">TCP/IP Task Offload</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities">OID_TCP_OFFLOAD_HARDWARE_CAPABILITIES</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_ipsec_offload_v2.md">NDIS_IPSEC_OFFLOAD_V2</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_ipsec_offload_v1.md">NDIS_IPSEC_OFFLOAD_V1</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_tcp_large_send_offload_v1.md">
   NDIS_TCP_LARGE_SEND_OFFLOAD_V1</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_tcp_ip_checksum_offload.md">NDIS_TCP_IP_CHECKSUM_OFFLOAD</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/jj991956">Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload</a>



<a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a>



<a href="https://msdn.microsoft.com/043A09F9-7D5D-4401-9645-19FDBD614659">Determining the RSC Capabilities of a Network Adapter</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_tcp_large_send_offload_v2.md">
   NDIS_TCP_LARGE_SEND_OFFLOAD_V2</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569762">OID_OFFLOAD_ENCAPSULATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_OFFLOAD structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>