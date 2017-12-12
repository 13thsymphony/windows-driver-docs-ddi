---
UID: NS.NTDDNDIS._NDIS_OFFLOAD
title: _NDIS_OFFLOAD
author: windows-driver-content
description: The NDIS_OFFLOAD structure specifies several computational tasks that can be offloaded to the network adapter.
old-location: netvista\ndis_offload.htm
old-project: netvista
ms.assetid: 9d1447f1-aae8-4c27-a27b-e521c0c8ca97
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_OFFLOAD, *PNDIS_OFFLOAD, NDIS_OFFLOAD
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
req.alt-api: NDIS_OFFLOAD
req.alt-loc: Ntddndis.h
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
---

# _NDIS_OFFLOAD structure



## -description
The NDIS_OFFLOAD structure specifies several computational <a href="netvista.task_offload">tasks that can be offloaded to the network adapter</a>.



## -syntax

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


## -struct-fields

### -field Header

The 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_OFFLOAD</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_OFFLOAD.
     

Set the <b>Revision</b> and <b>Size</b> members of the <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure as follows:<ul>
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



### -field Checksum

Checksum offload information in an 
     <a href="netvista.ndis_tcp_ip_checksum_offload">
     NDIS_TCP_IP_CHECKSUM_OFFLOAD</a> structure.


### -field LsoV1

Large send offload version 1 (LSOV1) information in an 
     <a href="netvista.ndis_tcp_large_send_offload_v1">
     NDIS_TCP_LARGE_SEND_OFFLOAD_V1</a> structure.


### -field IPsecV1

Internet protocol security (IPsec) offload information in an 
     <a href="netvista.ndis_ipsec_offload_v1">
     NDIS_IPSEC_OFFLOAD_V1</a> structure.


### -field LsoV2

Large send offload version 2 (LSOV2) offload information in an 
     <a href="netvista.ndis_tcp_large_send_offload_v2">
     NDIS_TCP_LARGE_SEND_OFFLOAD_V2</a> structure.


### -field Flags

A bitwise OR  of flags that specify properties that the network adapter supports. The following flags are defined.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field IPSEC_OFFLOAD_V2_AND_TCP_CHECKSUM_COEXISTENCE
### -field 0x00000002

</td>
<td width="60%">
The network adapter supports IPsecV2 and TCP checksums.

</td>
</tr>
<tr>

### -field IPSEC_OFFLOAD_V2_AND_UDP_CHECKSUM_COEXISTENCE
### -field 0x00000004

</td>
<td width="60%">
The network adapter supports IPsecV2 and UDP checksums.

</td>
</tr>
</table>
 


### -field IPsecV2

Internet protocol security (IPsec) offload version 2 information in an 
      <a href="netvista.ndis_ipsec_offload_v2">NDIS_IPSEC_OFFLOAD_V2</a> structure.


### -field Rsc


<a href="netvista.receive_segment_coalescing__rsc_">Receive Segment Coalescing (RSC)</a> offload information in    an <a href="netvista.ndis_tcp_recv_seg_coalesce_offload">NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD</a> structure.


### -field EncapsulatedPacketTaskOffloadGre


<a href="netvista.network_virtualization_using_generic_routing_encapsulation__nvgre__task_offload">Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload</a> information in an <a href="netvista.ndis_encapsulated_packet_task_offload">NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD</a> structure. This member should only be set by miniport drivers that support task offloads for NVGRE-formatted packets.<div class="alert"><b>Note</b>  This member is available only in NDIS 6.30 and later. </div>
<div> </div>



## -remarks
The <b>NDIS_OFFLOAD</b> structure is used in the following places:<ul>
<li>The <b>DefaultOffloadConfiguration</b> member of the <a href="netvista.ndis_miniport_adapter_offload_attributes">NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure</li>
<li>The <b>DefaultOffloadConfiguration</b> member of the <a href="netvista.ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure</li>
<li>The <b>DefaultOffloadConfiguration</b> member of the <a href="netvista.ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a> structure</li>
<li>The <b>InformationBuffer</b> member of the <a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a> structure (which is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569805">OID_TCP_OFFLOAD_CURRENT_CONFIG</a> OID request)</li>
<li>The <b>StatusBuffer</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567424">NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication</li>
</ul>



## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows Vista

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2008

</td>
</tr>
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
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndis_ipsec_offload_v1">NDIS_IPSEC_OFFLOAD_V1</a>
</dt>
<dt>
<a href="netvista.ndis_ipsec_offload_v2">NDIS_IPSEC_OFFLOAD_V2</a>
</dt>
<dt>
<a href="netvista.ndis_miniport_adapter_offload_attributes">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="netvista.ndis_status_indication">NDIS_STATUS_INDICATION</a>
</dt>
<dt>
<a href="netvista.ndis_status_task_offload_current_config">
   NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a>
</dt>
<dt>
<a href="netvista.ndis_tcp_ip_checksum_offload">NDIS_TCP_IP_CHECKSUM_OFFLOAD</a>
</dt>
<dt>
<a href="netvista.ndis_tcp_large_send_offload_v1">
   NDIS_TCP_LARGE_SEND_OFFLOAD_V1</a>
</dt>
<dt>
<a href="netvista.ndis_tcp_large_send_offload_v2">
   NDIS_TCP_LARGE_SEND_OFFLOAD_V2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569762">OID_OFFLOAD_ENCAPSULATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569805">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569806">OID_TCP_OFFLOAD_HARDWARE_CAPABILITIES</a>
</dt>
<dt>
<a href="netvista.determining_the_rsc_capabilities_of_a_network_adapter">Determining the RSC Capabilities of a Network Adapter</a>
</dt>
<dt>
<a href="netvista.network_virtualization_using_generic_routing_encapsulation__nvgre__task_offload">Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload</a>
</dt>
<dt>
<a href="netvista.task_offload">TCP/IP Task Offload</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_OFFLOAD structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

