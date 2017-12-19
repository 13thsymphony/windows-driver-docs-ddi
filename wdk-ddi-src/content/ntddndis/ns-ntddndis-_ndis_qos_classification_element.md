---
UID: NS.NTDDNDIS._NDIS_QOS_CLASSIFICATION_ELEMENT
title: _NDIS_QOS_CLASSIFICATION_ELEMENT
author: windows-driver-content
description: The NDIS_QOS_CLASSIFICATION_ELEMENT structure specifies an NDIS Quality of Service (QoS) traffic classification for a network adapter that supports the IEEE 802.1 Data Center Bridging (DCB) interface.Each traffic classification specifies the following:A classification condition that is based on a data pattern within the egress packet data.Starting with NDIS 6.30, classification conditions are based on a 16-bit value, such as a UDP or TCP destination port or a media access control (MAC) EtherType.A classification action that defines the traffic class to be used to handle the egress packet.Starting with NDIS 6.30, classification actions specify an 802.1p priority level.For example, a traffic classification could specify that all egress packets for destination TCP port number 3260 (condition) are assigned an 802.1p priority level 3 (action).
old-location: netvista\ndis_qos_classification_element.htm
old-project: NetVista
ms.assetid: 2677dc3a-7685-40bf-94c3-2efecf21e9a8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_QOS_CLASSIFICATION_ELEMENT, PNDIS_QOS_CLASSIFICATION_ELEMENT, NDIS_QOS_CLASSIFICATION_ELEMENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_QOS_CLASSIFICATION_ELEMENT
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

# _NDIS_QOS_CLASSIFICATION_ELEMENT structure



## -description

The <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structure specifies an NDIS Quality of Service (QoS) traffic classification for a network adapter that supports the IEEE 802.1 Data Center Bridging (DCB) interface.

Each traffic classification specifies the following:

<ul>
<li>
A classification <i>condition</i> that is based on a data pattern within the egress packet data.

Starting with NDIS 6.30, classification conditions are based on a 16-bit value, such as a UDP or TCP destination port or a media access control (MAC) EtherType.

</li>
<li>
A classification <i>action</i> that defines the traffic class to be used to handle the egress packet.

Starting with NDIS 6.30, classification actions specify an 802.1p priority level.

</li>
</ul>
For example, a traffic classification could specify that all egress packets for  destination TCP port number 3260 (<i>condition</i>) are assigned an 802.1p priority level 3 (<i>action</i>).



The <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structure specifies an NDIS Quality of Service (QoS) traffic classification for a network adapter that supports the IEEE 802.1 Data Center Bridging (DCB) interface.

Each traffic classification specifies the following:

A classification <i>condition</i> that is based on a data pattern within the egress packet data.

Starting with NDIS 6.30, classification conditions are based on a 16-bit value, such as a UDP or TCP destination port or a media access control (MAC) EtherType.

A classification <i>action</i> that defines the traffic class to be used to handle the egress packet.

Starting with NDIS 6.30, classification actions specify an 802.1p priority level.

For example, a traffic classification could specify that all egress packets for  destination TCP port number 3260 (<i>condition</i>) are assigned an 802.1p priority level 3 (<i>action</i>).



## -syntax

````
typedef struct _NDIS_QOS_CLASSIFICATION_ELEMENT {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  USHORT             ConditionSelector;
  USHORT             ConditionField;
  USHORT             ActionSelector;
  USHORT             ActionField;
} NDIS_QOS_CLASSIFICATION_ELEMENT, *PNDIS_QOS_CLASSIFICATION_ELEMENT;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structure. This member is formatted as an <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_QOS_CLASSIFICATION_ELEMENT. To specify the version of the <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 




### -field NDIS_QOS_CLASSIFICATION_ELEMENT_REVISION_1

Original version for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_QOS_CLASSIFICATION_ELEMENT_REVISION_1.

</dd>
</dl>

### -field Flags

A <b>ULONG</b> value that contains a bitwise OR of flags that specify the state of the NDIS QoS traffic classifications that a miniport driver supports. The following flags are defined:




### -field NDIS_QOS_CLASSIFICATION_ENFORCED_BY_MINIPORT

If this flag is set, the miniport driver accepts the traffic classification parameters that are specified in the <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structure. If the driver accepts the parameters, it must configure the network adapter to perform the traffic classification as specified by the parameters.

<div class="alert"><b>Note</b>  This flag is set only in the <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structures that the miniport driver returns to NDIS from an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451835">OID_QOS_PARAMETERS</a> OID method request.
</div>
<div> </div>
</dd>
</dl>

### -field ConditionSelector

A <b>USHORT</b> value that specifies the type of the data pattern that is contained in the <b>ConditionField</b> member. For example, the data pattern type could specify a destination UDP port whose value is specified by the <b>ConditionField</b> member.

For more information, see <a href="#condition_members">Guidelines for Setting the <b>ConditionSelector</b> and <b>ConditionField</b> Members</a>.


### -field ConditionField

A <b>USHORT</b> value that contains the data pattern whose type is specified by the  <b>ConditionSelector</b> member. 

For more information, see <a href="#condition_members">Guidelines for Setting the <b>ConditionSelector</b> and <b>ConditionField</b> Members</a>.


### -field ActionSelector

A <b>USHORT</b> value that specifies the type of action data that is contained in the <b>ActionField</b> member.  Starting with NDIS 6.30, the action data type specifies an 802.1p priority level whose value is specified by the <b>ConditionField</b> member.

For more information, see <a href="#action_members">Guidelines for Setting the <b>ActionSelector</b> and <b>ActionField</b> Members</a>.


### -field ActionField

A <b>USHORT</b> value that contains an action value whose type is specified by the  <b>ActionSelector</b> member.  

For more information, see <a href="#action_members">Guidelines for Setting the <b>ActionSelector</b> and <b>ActionField</b> Members</a>.


## -remarks
A traffic classification specifies a <i>condition</i> and an <i>action</i> that the network adapter applies to egress packet data. When the adapter inspects the egress packet data and finds a matching classification condition, it applies the corresponding action to the egress packet.

The <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structure specifies each traffic classification element within the array that is specified by the  <a href="netvista.ndis_qos_parameters">NDIS_QOS_PARAMETERS</a> structure. This structure is used in the following OID requests:

OID query requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451832">OID_QOS_OPERATIONAL_PARAMETERS</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh451841">OID_QOS_REMOTE_PARAMETERS</a>.

OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451835">OID_QOS_PARAMETERS</a>.

The miniport driver also returns an <a href="netvista.ndis_qos_parameters">NDIS_QOS_PARAMETERS</a> structure that contains an array of <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structures in the following NDIS status indications:


<a href="https://msdn.microsoft.com/library/windows/hardware/hh439810">NDIS_STATUS_QOS_OPERATIONAL_PARAMETERS_CHANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439812">NDIS_STATUS_QOS_REMOTE_PARAMETERS_CHANGE</a>


For more information, see <a href="netvista.ndis_qos_traffic_classifications">NDIS QoS Traffic Classifications</a>.

The following table defines the range of values for the <b>ConditionSelector</b> and <b>ConditionField</b> members.

The <b>ConditionField</b> member must be set to zero.

The <b>ConditionField</b> member must be set to zero. 

The <b>ConditionField</b> member contains a 16-bit destination TCP port value.

The <b>ConditionField</b> member contains a 16-bit destination UDP port value.

The <b>ConditionField</b> member contains a 16-bit destination TCP or UDP port value.

The <b>ConditionField</b> member contains a 16-bit IEEE EtherType value.

The <b>ConditionField</b> member contains a 16-bit NetworkDirect port value.

If the <b>ConditionSelector</b> member contains a value of NDIS_QOS_CONDITION_DEFAULT, the associated classification action must be applied to all egress packets that did not match any other classification conditions. When the DCB component issues an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451835">OID_QOS_PARAMETERS</a>, it may set the  <b>ConditionSelector</b> to NDIS_QOS_CONDITION_DEFAULT in only the first <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structure in the <a href="netvista.ndis_qos_parameters">NDIS_QOS_PARAMETERS</a> array.

If the <b>ConditionSelector</b> member contains a value of NDIS_QOS_CONDITION_NETDIRECT_PORT, the miniport driver must match the <b>ConditionField</b> member against either the source or destination port of a NetworkDirect connection. If the miniport driver accepts a NetDirect connection, the driver must match the <b>ConditionField</b> member against the source port of any packet it sends over that connection. If the miniport driver initiates a NetDirect connection, it must match the <b>ConditionField</b> member against the destination port of any packet it sends over that connection.

For more information on the DCB component, see <a href="netvista.ndis_qos_architecture_for_data_center_bridging">NDIS QoS Architecture for Data Center Bridging</a>.

The following table defines the range of values for the <b>ActionSelector</b> and <b>ActionField</b> members.

The <b>ActionField</b> member contains a 3-bit IEEE 802.1p priority level value. For more information on these priority levels, see <a href="netvista.ieee_802_1p_priority_levels">IEEE 802.1p Priority Levels</a>.

Starting with NDIS 6.30, traffic classification actions define an IEEE 802.1p priority level to which the egress packet is assigned. When the network adapter assigns a priority level to an egress packet, the adapter also applies the parameters for the NDIS QoS traffic class associated with the specified priority level. These parameters determine how the network adapter transmits the packet, and include bandwidth allocation  and transmission selection algorithm (TSA). 

For more information on NDIS QoS traffic classes, see <a href="netvista.ndis_qos_traffic_classes">NDIS QoS Traffic Classes</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.30 and later.

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
<dt><b></b></dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndis_qos_parameters">NDIS_QOS_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439810">NDIS_STATUS_QOS_OPERATIONAL_PARAMETERS_CHANGE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439812">NDIS_STATUS_QOS_REMOTE_PARAMETERS_CHANGE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451832">OID_QOS_OPERATIONAL_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451835">OID_QOS_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451841">OID_QOS_REMOTE_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_QOS_CLASSIFICATION_ELEMENT structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

