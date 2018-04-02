---
UID: NS:ntddndis._NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD
title: "_NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD"
author: windows-driver-content
description: The NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD structure contains the offload support state for Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload (NVGRE-TO).
old-location: netvista\ndis_encapsulated_packet_task_offload.htm
old-project: netvista
ms.assetid: EA13DADC-ED00-435D-BEA7-B6E52A86031A
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD, NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD, NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD structure [Network Drivers Starting with Windows Vista], PNDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD, PNDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD structure pointer [Network Drivers Starting with Windows Vista], _NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD, netvista.ndis_encapsulated_packet_task_offload, ntddndis/NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD, ntddndis/PNDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
-	ntddndis.h
api_name:
-	NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD
product:
- Windows
targetos: Windows
req.typenames: NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD, *PNDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD
---

# _NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD structure
The <b>NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD</b> structure contains the offload support state for <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/jj991956">Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload</a> (NVGRE-TO). This structure is used in the <b>EncapsulatedPacketTaskOffloadGre</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566599">NDIS_OFFLOAD</a> structure.

## Syntax
```
typedef struct _NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD {
  ULONG  : 4 TransmitChecksumOffloadSupported;
  ULONG  : 4 ReceiveChecksumOffloadSupported;
  ULONG  : 4 LsoV2Supported;
  ULONG  : 4 RssSupported;
  ULONG  : 4 VmqSupported;
  ULONG      MaxHeaderSizeSupported;
} *PNDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD, NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD;
```

## Members


`TransmitChecksumOffloadSupported`

Task offload settings for transmit checksum.

`ReceiveChecksumOffloadSupported`

Task offload settings for receive checksum.

`LsoV2Supported`

Task offload settings for large send offload version 2 (LSOv2).

`RssSupported`

Task offload settings for receive side scaling (RSS).

`VmqSupported`

Task offload settings for virtual machine queue (VMQ).

`MaxHeaderSizeSupported`

This member should be set to the maximum header size from the beginning of the packet to the beginning of the inner TCP or UDP payload (the last byte of TCP or UDP inner header) that the NIC must support for all of these task offloads. The protocol driver is expected to not offload processing of a packet whose combined encapsulation headers exceed this size. 

<div class="alert"><b>Note</b>  256 bytes is a good default value that should cover all possible cases.</div>
<div> </div>

## Remarks
In the initial capability advertisement and in <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567424">NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567425">NDIS_STATUS_TASK_OFFLOAD_HARDWARE_CAPABILITIES</a> status indications, the <b>TransmitChecksumOffloadSupported</b>, <b>ReceiveChecksumOffloadSupported</b>, <b>LsoV2Supported</b>, <b>RssSupported</b>, and <b>VmqSupported</b> members can be set to a bitwise OR of the following flags:




<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_NOT_SUPPORTED"></a><a id="ndis_encapsulated_packet_task_offload_not_supported"></a>NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_NOT_SUPPORTED

</td>
<td width="60%">
Specifies that the miniport adapter does not support the corresponding task offload feature that the member specifies.

</td>
</tr>
<tr>
<td width="40%">
<a id="NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_INNER_IPV4"></a><a id="ndis_encapsulated_packet_task_offload_inner_ipv4"></a>NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_INNER_IPV4

</td>
<td width="60%">
Specifies that the miniport adapter supports the corresponding task offload feature that the member specifies where the inner IP header of an encapsulated packet is IPv4.

</td>
</tr>
<tr>
<td width="40%">
<a id="NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_OUTER_IPV4"></a><a id="ndis_encapsulated_packet_task_offload_outer_ipv4"></a>NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_OUTER_IPV4

</td>
<td width="60%">
Specifies that the miniport adapter supports the corresponding task offload feature that the member specifies where the outer IP header of an encapsulated packet is IPv4.

</td>
</tr>
<tr>
<td width="40%">
<a id="NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_INNER_IPV6"></a><a id="ndis_encapsulated_packet_task_offload_inner_ipv6"></a>NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_INNER_IPV6

</td>
<td width="60%">
Specifies that the miniport adapter supports the corresponding task offload feature that the member specifies where the inner IP header of an encapsulated packet is IPv6.

</td>
</tr>
<tr>
<td width="40%">
<a id="NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_OUTER_IPV6"></a><a id="ndis_encapsulated_packet_task_offload_outer_ipv6"></a>NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_OUTER_IPV6

</td>
<td width="60%">
Specifies that the miniport adapter supports the corresponding task offload feature that the member specifies where the outer IP header of an encapsulated packet is IPv6.

</td>
</tr>
</table>
 



As an example, if a miniport adapter and driver only support an  IPv6 header as outer IP header but not as inner IP header, it will set <b>TransmitChecksumOffloadSupported</b>, <b>ReceiveChecksumOffloadSupported</b>, <b>LsoV2Supported</b>, <b>RssSupported</b>, and <b>VmqSupported</b> to the value of the bitwise OR of NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_INNER_IPV4, NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_OUTER_IPV4 and NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_OUTER_IPV6.

Regarding IP options and TCP options, the following assumption was made for encapsulated packets:<ul>
<li>If the NIC specifies <b>IpOptions</b> and <b>TcpOptions</b> support in normal checksum offload and LSOv2 advertisement, it must support the option processing for encapsulated packets if <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/jj991956">Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload</a> is supported. This means it will support both inner and outer IP options and TCP options inside the encapsulated packets. There is no separate capability advertisement for these specific to only NVGRE Task Offload.</li>
</ul>


It is possible for a protocol driver to offload "mixed mode" packets which means packets in which the inner and outer IP header versions are different. For example, a packet could have outer IP header as IPv6 and the inner IP header as IPv4.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8,Supported in NDIS 6.30 and later. Windows 8,Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566599">NDIS_OFFLOAD</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/jj991956">Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload</a>