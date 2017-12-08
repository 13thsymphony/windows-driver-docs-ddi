---
UID: NS.NTDDNDIS._NDIS_RECEIVE_FILTER_PARAMETERS
title: _NDIS_RECEIVE_FILTER_PARAMETERS
author: windows-driver-content
description: The NDIS_RECEIVE_FILTER_PARAMETERS structure specifies the parameters for an NDIS receive filter.
old-location: netvista\ndis_receive_filter_parameters.htm
old-project: netvista
ms.assetid: 39dc6b3a-f24d-4f1a-96f8-416fbcb3f894
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDIS_RECEIVE_FILTER_PARAMETERS, NDIS_RECEIVE_FILTER_PARAMETERS, *PNDIS_RECEIVE_FILTER_PARAMETERS
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
req.alt-api: NDIS_RECEIVE_FILTER_PARAMETERS
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

# _NDIS_RECEIVE_FILTER_PARAMETERS structure



## -description

The <b>NDIS_RECEIVE_FILTER_PARAMETERS</b> structure specifies the parameters for an NDIS receive filter.

The <b>NDIS_RECEIVE_FILTER_PARAMETERS</b> structure specifies the parameters for an NDIS receive filter.
NDIS receive filters are used in the following NDIS interfaces:

<a href="netvista.ndis_packet_coalescing">NDIS Packet Coalescing</a>. For more information on how to use receive filters in this technology, see <a href="netvista.managing_packet_coalescing_receive_filters">Managing Packet Coalescing Receive Filters</a>.

<a href="netvista.single_root_i_o_virtualization__sr-iov_">Single Root I/O Virtualization (SR-IOV)</a>. For more information on how to use receive filters in this technology, see <a href="netvista.setting_a_receive_filter_on_a_virtual_port">Setting a Receive Filter on a Virtual Port</a>.

<a href="netvista.virtual_machine_queue__vmq__in_ndis_6_20">Virtual Machine Queue (VMQ)</a>. For more information about how to use receive filters in this interface, see <a href="netvista.setting_and_clearing_vmq_filters">Setting and Clearing VMQ Filters</a>.


## -syntax

````
typedef struct _NDIS_RECEIVE_FILTER_PARAMETERS {
  NDIS_OBJECT_HEADER       Header;
  ULONG                    Flags;
  NDIS_RECEIVE_FILTER_TYPE FilterType;
  NDIS_RECEIVE_QUEUE_ID    QueueId;
  NDIS_RECEIVE_FILTER_ID   FilterId;
  ULONG                    FieldParametersArrayOffset;
  ULONG                    FieldParametersArrayNumElements;
  ULONG                    FieldParametersArrayElementSize;
  ULONG                    RequestedFilterIdBitCount;
#if (NDIS_SUPPORT_NDIS630)
  ULONG                    MaxCoalescingDelay;
  NDIS_NIC_SWITCH_VPORT_ID VPortId;
#endif 
} NDIS_RECEIVE_FILTER_PARAMETERS, *PNDIS_RECEIVE_FILTER_PARAMETERS;
````


## -struct-fields

### -field Header

The 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_FILTER_PARAMETERS</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT.
To indicate the version of the <b>NDIS_RECEIVE_FILTER_PARAMETERS</b> structure, the driver sets the 
     <b>Revision</b> member to one of the following values:


### -field NDIS_RECEIVE_FILTER_PARAMETERS_REVISION_2

Added the 
        <b>VPortId</b> and <b>MaxCoalescingDelay</b> members for NDIS 6.30.
The driver sets the 
        <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_PARAMETERS_REVISION_2.

### -field NDIS_RECEIVE_FILTER_PARAMETERS_REVISION_1

Original version for NDIS 6.20.
The driver sets the 
        <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_PARAMETERS_REVISION_1.
</dd>
</dl>

### -field Flags

A bitwise OR of the following flags.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field NDIS_RECEIVE_FILTER_PACKET_ENCAPSULATION_GRE
### -field 0x00000002

</td>
<td width="60%">
If this flag is set on the receive filter, the network adapter  must match this MAC address in the inner Ethernet frame in GRE encapsulated packets.
</td>
</tr>
</table>
 

### -field FilterType

The type of the receive filter.

### -field QueueId

A receive queue identifier. This identifier is an
     integer between zero and the number of queues that the network adapter supports. A value of NDIS_DEFAULT_RECEIVE_QUEUE_ID specifies
     the default receive queue.
<div class="alert"><b>Note</b>  Miniport drivers that support <a href="netvista.ndis_packet_coalescing">NDIS packet coalescing</a> or the SR-IOV interface must set the <b>QueueId</b> member to NDIS_DEFAULT_RECEIVE_QUEUE_ID.</div>
<div> </div>

### -field FilterId

A receive filter identifier. The filter identifier
     is an integer from one to the number of receive filters that the network adapter supports. A value of zero is
     invalid.

### -field FieldParametersArrayOffset

The offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_RECEIVE_FILTER_PARAMETERS</b> structure up to the beginning of the first element. Each element in the array is an <a href="netvista.ndis_receive_filter_field_parameters">NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.


<div class="alert"><b>Note</b>  If <b>FieldParametersArrayNumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field FieldParametersArrayNumElements

The number of elements in the array.

### -field FieldParametersArrayElementSize

The size, in bytes, of each element in the array.

### -field RequestedFilterIdBitCount

The number of bits in a filter identifier. The miniport driver uses
     this number of bits for the filter identifier in the 
     <b>NetBufferListFilteringInfo</b> out-of-band (OOB) data in 
     <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures.  If this member is zero, a miniport driver must not specify the filter identifier
     in the OOB 
     <b>NetBufferListFilteringInfo</b> data.
Starting with NDIS 6.20, this member must be set to zero.

### -field MaxCoalescingDelay

The maximum time, in milliseconds, that the first packet that matches this receive filter is saved within the hardware coalescing buffer on the network adapter. 
As soon as the first  packet that matches the filter is received, the network adapter coalesces the packet. The adapter also starts a hardware timer whose expiration time  is set to the value of the <b>MaxCoalescingDelay</b> member. Additional packets that match the same filter must be coalesced by the adapter without resetting and restarting the hardware timer.
When the hardware timer expires, the adapter must generate a receive interrupt to signal the host about coalesced packets that match the receive filter.
<div class="alert"><b>Note</b>  Miniport drivers that do not support <a href="netvista.ndis_packet_coalescing">NDIS packet coalescing</a> must ignore this member.</div>
<div> </div>

### -field VPortId

The VPort identifier on which the receive filter is to be configured. A value of DEFAULT_VPORT_ID specifies the default VPort that is attached to the PCI Express (PCIe) physical function (PF) of the network adapter.


<div class="alert"><b>Note</b>  This member is valid only for the SR-IOV interface.</div>
<div> </div>

## -remarks
The <b>NDIS_RECEIVE_FILTER_PARAMETERS</b> structure is used with OID requests of  
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569792">OID_RECEIVE_FILTER_PARAMETERS</a>
    and  
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569795">OID_RECEIVE_FILTER_SET_FILTER</a>. These OID
    requests specify the configuration parameters of a filter. A filter specification can include tests for
    multiple fields in a network packet.

The 
    <b>FieldParametersArrayOffset</b>, 
    <b>FieldParametersArrayNumElements</b>, and 
    <b>FieldParametersArrayElementSize</b> members of the <b>NDIS_RECEIVE_FILTER_PARAMETERS</b> structure define an
    array of 
    <a href="netvista.ndis_receive_filter_field_parameters">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structures. Each <b>NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</b>
    structure in the array sets the filter test criterion for one field in a network header.

The network adapter combines the results from all the field tests with a logical AND operation.
    That is, if any field test that is included in the array of <a href="netvista.ndis_receive_filter_field_parameters">NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>
    structures fails, the network packet does not meet the specified filter criterion.

When a network adapter tests a received packet against these filter criteria, it must ignore all
    the fields in the packet where no test criterion is specified.

If the packet meets the filter criterion, the network adapter must do one of the following:<ul>
<li>
If the network adapter supports NDIS receive packet coalescing, the adapter must coalesce the packet that matches the filter. The adapter must also coalesce received packets that match the same or different receive filters. The adapter must withhold on generating the receive interrupt until  another  hardware event occurs, such as the following:<ul>
<li>
The expiration of a hardware timer whose expiration time  is set to the value of the <b>MaxCoalescingDelay</b> member.
</li>
<li>
The available space within the hardware coalescing buffer reaches an adapter-specific low-water mark.
</li>
</ul>

For more information, see <a href="netvista.handling_packet_coalescing_receive_filters">Handling Packet Coalescing Receive Filters</a>.
</li>
<li>
If the network adapter supports the SR-IOV interface, the adapter should forward the packet to the receive queue of a default or nondefault VPort. The receive queue is specified by the <b>QueueId</b> member and the VPort is specified by the  <b>VPortId</b> member.
<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the SR-IOV interface supports only the default receive queue on both default and nondefault VPorts. The default receive queue is specified by setting the <b>QueueId</b> member to NDIS_DEFAULT_RECEIVE_QUEUE_ID.</div>
<div> </div>
</li>
<li>
If the network adapter supports the VMQ interface, the  adapter should forward the packet to the receive queue specified by the <b>QueueId</b> member.
</li>
</ul>


If the network adapter supports NDIS receive packet coalescing, the adapter must coalesce the packet that matches the filter. The adapter must also coalesce received packets that match the same or different receive filters. The adapter must withhold on generating the receive interrupt until  another  hardware event occurs, such as the following:<ul>
<li>
The expiration of a hardware timer whose expiration time  is set to the value of the <b>MaxCoalescingDelay</b> member.
</li>
<li>
The available space within the hardware coalescing buffer reaches an adapter-specific low-water mark.
</li>
</ul>


The expiration of a hardware timer whose expiration time  is set to the value of the <b>MaxCoalescingDelay</b> member.

The available space within the hardware coalescing buffer reaches an adapter-specific low-water mark.

For more information, see <a href="netvista.handling_packet_coalescing_receive_filters">Handling Packet Coalescing Receive Filters</a>.

If the network adapter supports the SR-IOV interface, the adapter should forward the packet to the receive queue of a default or nondefault VPort. The receive queue is specified by the <b>QueueId</b> member and the VPort is specified by the  <b>VPortId</b> member.

If the network adapter supports the VMQ interface, the  adapter should forward the packet to the receive queue specified by the <b>QueueId</b> member.

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
<a href="netvista.ndis_receive_filter_field_parameters">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569792">OID_RECEIVE_FILTER_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569795">OID_RECEIVE_FILTER_SET_FILTER</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_FILTER_PARAMETERS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
