---
UID: NE.fwpsk.FWPS_FIELDS_OUTBOUND_TRANSPORT_V4_
title: FWPS_FIELDS_OUTBOUND_TRANSPORT_V4_
author: windows-driver-content
description: The FWPS_FIELDS_OUTBOUND_TRANSPORT_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_OUTBOUND_TRANSPORT_V4 and FWPS_LAYER_OUTBOUND_TRANSPORT_V4_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_outbound_transport_v4.htm
old-project: netvista
ms.assetid: 1acb99a6-3fbb-4f2c-b38d-befb49749bea
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: FWPS_FIELDS_OUTBOUND_TRANSPORT_V4_, FWPS_FIELDS_OUTBOUND_TRANSPORT_V4
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Unless otherwise noted, supported starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_FIELDS_OUTBOUND_TRANSPORT_V4
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

# FWPS_FIELDS_OUTBOUND_TRANSPORT_V4_ enumeration



## -description
The FWPS_FIELDS_OUTBOUND_TRANSPORT_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_OUTBOUND_TRANSPORT_V4 and FWPS_LAYER_OUTBOUND_TRANSPORT_V4_DISCARD 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layers</a>.



## -syntax

````
typedef enum FWPS_FIELDS_OUTBOUND_TRANSPORT_V4_ { 
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_PROTOCOL,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_LOCAL_ADDRESS,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_LOCAL_ADDRESS_TYPE,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_REMOTE_ADDRESS,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_LOCAL_PORT,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_REMOTE_PORT,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_LOCAL_INTERFACE,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_INTERFACE_INDEX,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_SUB_INTERFACE_INDEX,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_DESTINATION_ADDRESS_TYPE,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_FLAGS,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_INTERFACE_TYPE,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_TUNNEL_TYPE,
#if (NTDDI_VERSION >= NTDDI_WIN7)
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_PROFILE_ID,
#endif 
  FWPS_FIELD_OUTBOUND_TRANSPORT_V4_MAX
} FWPS_FIELDS_OUTBOUND_TRANSPORT_V4;
````


## -enum-fields

### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_PROTOCOL

The IP protocol number, as specified in RFC 1700.


### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the 
     <a href="netvista.nl_address_type">NL_ADDRESS_TYPE</a> enumeration.


### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_LOCAL_PORT

The local transport protocol port number.


### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_REMOTE_PORT

The remote transport protocol port number.


### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="netvista.luid">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_INTERFACE_INDEX

The index of the network interface, as enumerated by the network stack.


### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_SUB_INTERFACE_INDEX

The index of the logical network interface, as enumerated by the network stack.


### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_IP_DESTINATION_ADDRESS_TYPE

The destination IP address type. The possible values are defined by the 
     <a href="netvista.nl_address_type">NL_ADDRESS_TYPE</a> enumeration.


### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a>.


### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_INTERFACE_TYPE

The type of the local network interface, as defined by the Internet Assigned Numbers Authority
     (IANA). For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.


### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_TUNNEL_TYPE

The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by IANA. For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
     Windows SDK.


### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_PROFILE_ID

The profile identifier (network category) of the network interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_OUTBOUND_TRANSPORT_V4_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks
The following macros in 
    <i>Fwpsk.h</i> are defined with FWPS_FIELDS_OUTBOUND_TRANSPORT_V4 enumeration
    values:

These macros are used to access the following IPV4 data fields:



The ICMP type field, as specified in RFC 792.

The ICMP code field, as specified in RFC 792.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Unless otherwise noted, supported starting with Windows Vista.

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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_FIELDS_OUTBOUND_TRANSPORT_V4 enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

