---
UID: NE.fwpsk.FWPS_FIELDS_OUTBOUND_IPPACKET_V6_
title: FWPS_FIELDS_OUTBOUND_IPPACKET_V6_
author: windows-driver-content
description: The FWPS_FIELDS_OUTBOUND_IPPACKET_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_OUTBOUND_IPPACKET_V6 and FWPS_LAYER_OUTBOUND_IPPACKET_V6_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_outbound_ippacket_v6.htm
old-project: NetVista
ms.assetid: 641b3663-2216-43b4-a2ab-1f94e31080ca
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FWPS_FIELDS_OUTBOUND_IPPACKET_V6_, FWPS_FIELDS_OUTBOUND_IPPACKET_V6
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_FIELDS_OUTBOUND_IPPACKET_V6
req.alt-loc: fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# FWPS_FIELDS_OUTBOUND_IPPACKET_V6_ enumeration



## -description
The FWPS_FIELDS_OUTBOUND_IPPACKET_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_OUTBOUND_IPPACKET_V6 and FWPS_LAYER_OUTBOUND_IPPACKET_V6_DISCARD 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layers</a>.



## -syntax

````
typedef enum FWPS_FIELDS_OUTBOUND_IPPACKET_V6_ { 
  FWPS_FIELD_OUTBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS,
  FWPS_FIELD_OUTBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS_TYPE,
  FWPS_FIELD_OUTBOUND_IPPACKET_V6_IP_REMOTE_ADDRESS,
  FWPS_FIELD_OUTBOUND_IPPACKET_V6_IP_LOCAL_INTERFACE,
  FWPS_FIELD_OUTBOUND_IPPACKET_V6_INTERFACE_INDEX,
  FWPS_FIELD_OUTBOUND_IPPACKET_V6_SUB_INTERFACE_INDEX,
  FWPS_FIELD_OUTBOUND_IPPACKET_V6_FLAGS,
  FWPS_FIELD_OUTBOUND_IPPACKET_V6_INTERFACE_TYPE,
  FWPS_FIELD_OUTBOUND_IPPACKET_V6_TUNNEL_TYPE,
  FWPS_FIELD_OUTBOUND_IPPACKET_V6_MAX
} FWPS_FIELDS_OUTBOUND_IPPACKET_V6;
````


## -enum-fields

### -field FWPS_FIELD_OUTBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_OUTBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the 
     <a href="netvista.nl_address_type">NL_ADDRESS_TYPE</a> enumeration


### -field FWPS_FIELD_OUTBOUND_IPPACKET_V6_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_OUTBOUND_IPPACKET_V6_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="netvista.luid">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_OUTBOUND_IPPACKET_V6_INTERFACE_INDEX

The index of the network interface, as enumerated by the network stack.


### -field FWPS_FIELD_OUTBOUND_IPPACKET_V6_SUB_INTERFACE_INDEX

The index of the logical network interface, as enumerated by the network stack.


### -field FWPS_FIELD_OUTBOUND_IPPACKET_V6_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a>.


### -field FWPS_FIELD_OUTBOUND_IPPACKET_V6_INTERFACE_TYPE

The type of the network interface, as defined by the Internet Assigned Numbers Authority (IANA).
     For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.


### -field FWPS_FIELD_OUTBOUND_IPPACKET_V6_TUNNEL_TYPE

The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by IANA. For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
     Windows SDK.


### -field FWPS_FIELD_OUTBOUND_IPPACKET_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows Vista.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.luid">LUID</a>
</dt>
<dt>
<a href="netvista.nl_address_type">NL_ADDRESS_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20FWPS_FIELDS_OUTBOUND_IPPACKET_V6 enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

