---
UID: NS.NTDDNDIS._NDIS_RECEIVE_FILTER_FIELD_PARAMETERS
title: _NDIS_RECEIVE_FILTER_FIELD_PARAMETERS
author: windows-driver-content
description: The NDIS_RECEIVE_FILTER_FIELD_PARAMETERS structure specifies the filter test criterion for a field in a network packet header.
old-location: netvista\ndis_receive_filter_field_parameters.htm
old-project: netvista
ms.assetid: 3d387fe9-a7cc-4034-b31e-ba1359db2ae1
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_RECEIVE_FILTER_FIELD_PARAMETERS, *PNDIS_RECEIVE_FILTER_FIELD_PARAMETERS, NDIS_RECEIVE_FILTER_FIELD_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_RECEIVE_FILTER_FIELD_PARAMETERS
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

# _NDIS_RECEIVE_FILTER_FIELD_PARAMETERS structure



## -description
The <b>NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</b> structure specifies the filter test criterion for a field
  in a network packet header.

NDIS receive filters are used in the following NDIS interfaces:


<a href="netvista.ndis_packet_coalescing">NDIS Packet Coalescing</a>. For more information about how to use receive filters in this interface, see <a href="netvista.managing_packet_coalescing_receive_filters">Managing Packet Coalescing Receive Filters</a>.


<a href="netvista.single_root_i_o_virtualization__sr-iov_">Single Root I/O Virtualization (SR-IOV)</a>. For more information about how to use receive filters in this interface, see <a href="netvista.setting_a_receive_filter_on_a_virtual_port">Setting a Receive Filter on a Virtual Port</a>.


<a href="netvista.virtual_machine_queue__vmq__in_ndis_6_20">Virtual Machine Queue (VMQ)</a>. For more information about how to use receive filters in this interface, see <a href="netvista.setting_and_clearing_vmq_filters">Setting and Clearing VMQ Filters</a>.



## -syntax

````
typedef struct _NDIS_RECEIVE_FILTER_FIELD_PARAMETERS {
  NDIS_OBJECT_HEADER       Header;
  ULONG                    Flags;
  NDIS_FRAME_HEADER        FrameHeader;
  NDIS_RECEIVE_FILTER_TEST ReceiveFilterTest;
  union _HEADER_FIELD {
    NDIS_MAC_HEADER_FIELD        MacHeaderField;
    NDIS_ARP_HEADER_FIELD        ArpHeaderField;
    NDIS_IPV4_HEADER_FIELD       IPv4HeaderField;
    NDIS_IPV6_HEADER_FIELD       IPv6HeaderField;
    NDIS_UDP_HEADER_FIELD        UdpHeaderField;
  } HeaderField;
  union _FIELD_VALUE {
    UCHAR   FieldByteValue;
    USHORT  FieldShortValue;
    ULONG   FieldLongValue;
    ULONG64 FieldLong64Value;
    UCHAR   FieldByteArrayValue[16];
  } FieldValue;
  union _RESULT_VALUE {
    UCHAR   ResultByteValue;
    USHORT  ResultShortValue;
    ULONG   ResultLongValue;
    ULONG64 ResultLong64Value;
    UCHAR   ResultByteArrayValue[16];
  } ResultValue;
} NDIS_RECEIVE_FILTER_FIELD_PARAMETERS, *PNDIS_RECEIVE_FILTER_FIELD_PARAMETERS;
````


## -struct-fields

### -field Header

The 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT.

To indicate the version of the <b>NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</b> structure, the driver sets the 
     <b>Revision</b> member to one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field NDIS_RECEIVE_FILTER_FIELD_PARAMETERS_REVISION_2
### -field 2

</td>
<td width="60%">
Added additional members to the <b>HeaderField</b> union for NDIS 6.30.

The driver sets the 
        <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_FILTER_FIELD_PARAMETERS_REVISION_2</b>.

</td>
</tr>
<tr>

### -field NDIS_RECEIVE_FILTER_FIELD_PARAMETERS_REVISION_1
### -field 1

</td>
<td width="60%">
Original version for NDIS 6.20.

The driver sets the 
        <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_FILTER_FIELD_PARAMETERS_REVISION_1</b>.

</td>
</tr>
</table>
 


### -field Flags

A bitwise OR of flags. The following flags are valid for the 
     <a href="netvista.oid_receive_filter_set_filter">
     OID_RECEIVE_FILTER_SET_FILTER</a> OID.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field NDIS_RECEIVE_FILTER_FIELD_MAC_HEADER_VLAN_UNTAGGED_OR_ZERO
### -field 0x00000001

</td>
<td width="60%">
If this flag is set, the network adapter must only indicate received packets that pass the following criteria:

<ul>
<li>
The packet's media access control (MAC) address matches the specified MAC header field test.

</li>
<li>
The packet either does not contain a VLAN tag or has a VLAN tag with an ID of zero. 

</li>
</ul>
For more information about this flag, see the Remarks section.

<div class="alert"><b>Note</b>  If an overlying driver sets a MAC address filter and a VLAN identifier filter with an
       OID request of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569795">OID_RECEIVE_FILTER_SET_FILTER</a>, it does not set this flag in either of the filter fields. In this
       case, the miniport driver should indicate packets that match both the specified MAC address and the
       VLAN identifier. That is, the miniport driver should not indicate packets with a matching MAC address
       that have a zero VLAN identifier or are untagged packets.</div>
<div> </div>
</td>
</tr>
</table>
 


### -field FrameHeader

The type of header in the network data frame.


### -field ReceiveFilterTest

The type of test to perform for the receive filter.


### -field HeaderField

The type of field in a header. The field type (for example,
     <a href="netvista.ndis_mac_header_field">NDIS_MAC_HEADER_FIELD</a>) corresponds to the type of header that is specified in the 
     <b>FrameHeader</b> member.
     

This union contains the following members:


### -field MacHeaderField

The type of field in a MAC header.


### -field ArpHeaderField

The type of field in an Address Resolution Protocol (ARP) header.


### -field IPv4HeaderField

An 
       <a href="netvista.ndis_ipv4_header_field">NDIS_IPV4_HEADER_FIELD</a> enumeration
       value that specifies the type of field in an IP version 4 (IPv4) header.


### -field IPv6HeaderField

An 
       <a href="netvista.ndis_ipv6_header_field">NDIS_IPV6_HEADER_FIELD</a> enumeration
       value that specifies the type of field in an IP version 6 (IPv6) header.


### -field UdpHeaderField

The type of field in a User Datagram Protocol
(UDP) header.

</dd>
</dl>

### -field FieldValue



The value that the miniport adapter compares to the corresponding header field value in incoming packets. The location of the header field value is determined by the field type that is specified in the <b>HeaderField</b> member.

For more information, see the Remarks section.

This union contains the following members:


### -field FieldByteValue

A <b>UCHAR</b> value to compare with a field in a network packet.

<div class="alert"><b>Note</b>  If the <b>MacHeaderField</b> member specifies an <b>NdisMacHeaderFieldPacketType</b> enumeration value, this member contains an <a href="netvista.ndis_mac_packet_type">NDIS_MAC_PACKET_TYPE</a> enumeration value.</div>
<div> </div>

### -field FieldShortValue

A <b>USHORT</b> value to compare with a field in a network packet.


### -field FieldLongValue

A <b>ULONG</b> value to compare with a field in a network packet.


### -field FieldLong64Value

A <b>ULONG64</b> value to compare with a field in a network packet.


### -field FieldByteArrayValue

A <b>UCHAR</b> array to compare with a field in a network packet.

</dd>
</dl>

### -field ResultValue

A union that contains a test result value. 

If the <b>ReceiveFilterTest</b> member is set to  <b>NdisReceiveFilterTestMaskEqual</b>, the network adapter first calculates a result from the value in the <b>FieldValue</b> member and the header field value as specified by the <b>HeaderField</b> member. The adapter then compares the calculated result with <b>ResultValue</b>. 

For more information, see the Remarks section.

This union contains the following members:


### -field ResultByteValue

A <b>UCHAR</b> value to compare with a test result.


### -field ResultShortValue

A <b>USHORT</b> value to compare with a test result.


### -field ResultLongValue

A <b>ULONG</b> value to compare with a test result.


### -field ResultLong64Value

A <b>ULONG64</b> value to compare with a test result.


### -field ResultByteArrayValue

A <b>UCHAR</b> array to compare with a test result.

</dd>
</dl>

## -remarks
The <b>NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</b> structure specifies the filter test criterion for one field
    in a possible array of field tests that can be specified with the 
    <a href="netvista.ndis_receive_filter_parameters">
    NDIS_RECEIVE_FILTER_PARAMETERS</a> structure.

The following table describes how the network adapter uses the <b>ReceiveFilterTest</b>, <b>FieldValue</b>, and <b>ResultValue</b> members to perform a filter test on the specified header field value of a received packet.

If the <b>NDIS_RECEIVE_FILTER_FIELD_MAC_HEADER_VLAN_UNTAGGED_OR_ZERO</b> flag is not set and there is no VLAN identifier filter that was configured by an OID set request of
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff569795">OID_RECEIVE_FILTER_SET_FILTER</a>, the miniport driver must do one of the following:

For NDIS 6.20, the miniport driver must return a failed status for the
       OID request of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569795">OID_RECEIVE_FILTER_SET_FILTER</a>.

Starting with NDIS 6.30, if the <b>NDIS_RECEIVE_FILTER_FIELD_MAC_HEADER_VLAN_UNTAGGED_OR_ZERO</b> flag is not set and there is no VLAN identifier filter configured by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569795">OID_RECEIVE_FILTER_SET_FILTER</a> method request, the miniport driver must do either one of the following:

The miniport driver must return a failed status for the
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff569795">OID_RECEIVE_FILTER_SET_FILTER</a> method request.

The miniport driver  must configure the network adapter  to inspect and filter the specified MAC address fields. If a VLAN tag is present in the received packet, the network adapter must remove it from the packet data. The miniport driver must   put the VLAN tag in an <a href="netvista.ndis_net_buffer_list_8021q_info">NDIS_NET_BUFFER_LIST_8021Q_INFO</a> that is associated with the packet's <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure.

Starting with NDIS 6.30, if the <b>NDIS_RECEIVE_FILTER_FIELD_MAC_HEADER_VLAN_UNTAGGED_OR_ZERO</b> flag is not set and there is a non-zero VLAN identifier filter that was configured by an OID set request of
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff569795">OID_RECEIVE_FILTER_SET_FILTER</a>, the miniport driver must do the following:

The miniport driver must configure the network adapter  to inspect and filter the specified MAC address and VLAN identifier fields. 

If a VLAN tag is present in the received packet, the network adapter must remove it from the packet data. The miniport driver must   put the VLAN tag in an <a href="netvista.ndis_net_buffer_list_8021q_info">NDIS_NET_BUFFER_LIST_8021Q_INFO</a> that is associated with the packet's <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.20 and later.

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
<a href="netvista.ndis_arp_header_field">NDIS_ARP_HEADER_FIELD</a>
</dt>
<dt>
<a href="netvista.ndis_frame_header">NDIS_FRAME_HEADER</a>
</dt>
<dt>
<a href="netvista.ndis_ipv4_header_field">NDIS_IPV4_HEADER_FIELD</a>
</dt>
<dt>
<a href="netvista.ndis_ipv6_header_field">NDIS_IPV6_HEADER_FIELD</a>
</dt>
<dt>
<a href="netvista.ndis_udp_header_field">NDIS_UDP_HEADER_FIELD</a>
</dt>
<dt>
<a href="netvista.ndis_mac_header_field">NDIS_MAC_HEADER_FIELD</a>
</dt>
<dt>
<a href="netvista.ndis_mac_packet_type">NDIS_MAC_PACKET_TYPE</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndis_receive_filter_parameters">
   NDIS_RECEIVE_FILTER_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndis_receive_filter_test">NDIS_RECEIVE_FILTER_TEST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569795">OID_RECEIVE_FILTER_SET_FILTER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_FILTER_FIELD_PARAMETERS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

