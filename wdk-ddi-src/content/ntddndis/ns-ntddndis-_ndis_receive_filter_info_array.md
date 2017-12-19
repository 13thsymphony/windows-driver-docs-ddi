---
UID: NS.NTDDNDIS._NDIS_RECEIVE_FILTER_INFO_ARRAY
title: _NDIS_RECEIVE_FILTER_INFO_ARRAY
author: windows-driver-content
description: The NDIS_RECEIVE_FILTER_INFO_ARRAY structure specifies a list of receive filters that are currently configured on a miniport driver.
old-location: netvista\ndis_receive_filter_info_array.htm
old-project: NetVista
ms.assetid: 32896b46-1143-4598-ad15-2eb4dbdea6e8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_RECEIVE_FILTER_INFO_ARRAY, *PNDIS_RECEIVE_FILTER_INFO_ARRAY, PNDIS_RECEIVE_FILTER_INFO_ARRAY, NDIS_RECEIVE_FILTER_INFO_ARRAY
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
req.alt-api: NDIS_RECEIVE_FILTER_INFO_ARRAY
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

# _NDIS_RECEIVE_FILTER_INFO_ARRAY structure



## -description

The <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure specifies a list of receive filters that are currently configured on a miniport driver.



The <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure specifies a list of receive filters that are currently configured on a miniport driver.

NDIS receive filters are used in the following NDIS interfaces:


<a href="netvista.ndis_packet_coalescing">NDIS Packet Coalescing</a>. For more information about how to use receive filters in this interface, see <a href="netvista.managing_packet_coalescing_receive_filters">Managing Packet Coalescing Receive Filters</a>.


<a href="netvista.single_root_i_o_virtualization__sr-iov_">Single Root I/O Virtualization (SR-IOV)</a>. For more information about how to use receive filters in this interface, see <a href="netvista.setting_a_receive_filter_on_a_virtual_port">Setting a Receive Filter on a Virtual Port</a>.


<a href="netvista.virtual_machine_queue__vmq__in_ndis_6_20">Virtual Machine Queue (VMQ)</a>. For more information about how to use receive filters in this interface, see <a href="netvista.setting_and_clearing_vmq_filters">Setting and Clearing VMQ Filters</a>.



## -syntax

````
typedef struct _NDIS_RECEIVE_FILTER_INFO_ARRAY {
  NDIS_OBJECT_HEADER       Header;
  NDIS_RECEIVE_QUEUE_ID    QueueId;
  ULONG                    FirstElementOffset;
  ULONG                    NumElements;
  ULONG                    ElementSize;
#if (NDIS_SUPPORT_NDIS630)
  ULONG                    Flags;
  NDIS_NIC_SWITCH_VPORT_ID VPortId;
#endif 
} NDIS_RECEIVE_FILTER_INFO_ARRAY, *PNDIS_RECEIVE_FILTER_INFO_ARRAY;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure. This member is formatted as an <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 




### -field NDIS_SIZEOF_RECEIVE_FILTER_INFO_ARRAY_REVISION_2

Added members for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_INFO_ARRAY_REVISION_2.


### -field NDIS_SIZEOF_RECEIVE_FILTER_INFO_ARRAY_REVISION_1

Original version for NDIS 6.20.

Set the <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_INFO_ARRAY_REVISION_1.

</dd>
</dl>

### -field QueueId

A receive queue identifier. This identifier is an
     integer between zero and the number of queues that the network adapter supports. A value of NDIS_DEFAULT_RECEIVE_QUEUE_ID specifies
     the default receive queue.

<div class="alert"><b>Note</b>  Miniport drivers that support <a href="netvista.ndis_packet_coalescing">NDIS packet coalescing</a> or SR-IOV interface must set the <b>QueueId</b> member to NDIS_DEFAULT_RECEIVE_QUEUE_ID.</div>
<div> </div>

### -field FirstElementOffset

The offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="netvista.ndis_receive_filter_info">NDIS_RECEIVE_FILTER_INFO</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field NumElements

The number of elements in the array.


### -field ElementSize

The size, in bytes, of each element in the array.


### -field Flags

A  bitwise OR of the following flags: 




### -field NDIS_RECEIVE_FILTER_INFO_ARRAY_VPORT_ID_SPECIFIED

If this flag is set, information is requested about receive filters that are configured on the virtual port (VPort) specified by the <b>VPortId</b> member.

<div class="alert"><b>Note</b>  This flag is only valid for the SR-IOV interface.</div>
<div> </div>
</dd>
</dl>

### -field VPortId

The virtual port (VPort) identifier on which receive filters are being queried. The VPort identifier must be one of the following values:

<ul>
<li>


The identifier of a VPort that was previously allocated through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>.



</li>
<li>
A value of NDIS_DEFAULT_VPORT_ID that specifies the default VPort on the NIC switch.



</li>
</ul>
A NIC switch is supported by network adapters for the SR-IOV interface. The NIC switch can be configured to have one or more VPorts.

<div class="alert"><b>Note</b>  The <b>VPortId</b> member is only valid if the NDIS_RECEIVE_FILTER_INFO_ARRAY_VPORT_ID_SPECIFIED flag is set in <b>Flags</b>. 
</div>
<div> </div>

## -remarks
The <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure is used in the 
    OID request of <a href="netvista.oid_receive_filter_enum_filters">
    OID_RECEIVE_FILTER_ENUM_FILTERS</a>. This OID request enumerates the receive filters on a VMQ  or SR-IOV receive queue. Each
    element in the array that follows the <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure is an 
    <a href="netvista.ndis_receive_filter_info">
    NDIS_RECEIVE_FILTER_INFO</a> structure.


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
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndis_receive_filter_info">NDIS_RECEIVE_FILTER_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569787">OID_RECEIVE_FILTER_ENUM_FILTERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_RECEIVE_FILTER_INFO_ARRAY structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

