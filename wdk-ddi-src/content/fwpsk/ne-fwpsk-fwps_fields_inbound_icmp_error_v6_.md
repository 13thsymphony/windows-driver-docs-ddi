---
UID: NE.fwpsk.FWPS_FIELDS_INBOUND_ICMP_ERROR_V6_
title: FWPS_FIELDS_INBOUND_ICMP_ERROR_V6_
author: windows-driver-content
description: The FWPS_FIELDS_INBOUND_ICMP_ERROR_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_INBOUND_ICMP_ERROR_V6 and FWPS_LAYER_INBOUND_ICMP_ERROR_V6_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_inbound_icmp_error_v6.htm
old-project: NetVista
ms.assetid: ffdd1cd9-0a03-4b5c-bc4e-f1067e2f2d7b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FWPS_FIELDS_INBOUND_ICMP_ERROR_V6_, FWPS_FIELDS_INBOUND_ICMP_ERROR_V6
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Unless otherwise noted, supported starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_FIELDS_INBOUND_ICMP_ERROR_V6
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

# FWPS_FIELDS_INBOUND_ICMP_ERROR_V6_ enumeration



## -description
The FWPS_FIELDS_INBOUND_ICMP_ERROR_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_INBOUND_ICMP_ERROR_V6 and FWPS_LAYER_INBOUND_ICMP_ERROR_V6_DISCARD 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layers</a>.



## -syntax

````
typedef enum FWPS_FIELDS_INBOUND_ICMP_ERROR_V6_ { 
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_EMBEDDED_PROTOCOL,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_IP_LOCAL_ADDRESS,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_IP_REMOTE_ADDRESS,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_EMBEDDED_REMOTE_ADDRESS,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_EMBEDDED_LOCAL_ADDRESS_TYPE,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_EMBEDDED_LOCAL_PORT,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_EMBEDDED_REMOTE_PORT,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_IP_LOCAL_INTERFACE,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_ICMP_TYPE,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_ICMP_CODE,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_INTERFACE_INDEX,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_SUB_INTERFACE_INDEX,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_INTERFACE_TYPE,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_TUNNEL_TYPE,
#if (NTDDI_VERSION >= NTDDI_WIN6SP1)
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_IP_ARRIVAL_INTERFACE,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_ARRIVAL_INTERFACE_INDEX,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_ARRIVAL_INTERFACE_TYPE,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_ARRIVAL_TUNNEL_TYPE,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_FLAGS,
#if (NTDDI_VERSION >= NTDDI_WIN7)
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_ARRIVAL_INTERFACE_PROFILE_ID,
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_INTERFACE_QUARANTINE_EPOCH,
#endif 
#endif 
  FWPS_FIELD_INBOUND_ICMP_ERROR_V6_MAX
} FWPS_FIELDS_INBOUND_ICMP_ERROR_V6;
````


## -enum-fields

### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_EMBEDDED_PROTOCOL

The IP protocol number that is embedded in the ICMP packet, as specified in RFC 1700.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_EMBEDDED_REMOTE_ADDRESS

The remote IP address that is embedded in the ICMP packet.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_EMBEDDED_LOCAL_ADDRESS_TYPE

The local IP address type that is embedded in the ICMP packet. The possible condition values are
     defined by the 
     <a href="netvista.nl_address_type">NL_ADDRESS_TYPE</a> enumeration.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_EMBEDDED_LOCAL_PORT

The local transport protocol port number that is embedded in the ICMP packet.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_EMBEDDED_REMOTE_PORT

The remote transport protocol port number that is embedded in the ICMP packet.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="netvista.luid">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_ICMP_TYPE

The ICMP type field, as specified in RFC 792.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_ICMP_CODE

The ICMP code field, as specified in RFC 792.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_INTERFACE_INDEX

The index of the local network interface, as enumerated by the network stack.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_SUB_INTERFACE_INDEX

The LUID for the network interface that is associated with the arrival IP address


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_INTERFACE_TYPE

The type of the local network interface, as defined by the Internet Assigned Numbers Authority
     (IANA). For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_TUNNEL_TYPE

The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by IANA. For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
     Windows SDK.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_IP_ARRIVAL_INTERFACE

The LUID for the network interface that is associated with the arrival IP address.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_ARRIVAL_INTERFACE_INDEX

The index of the arrival network interface, as enumerated by the network stack.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_ARRIVAL_INTERFACE_TYPE

The type of the arrival network interface, as defined by the Internet Assigned Numbers Authority
     (IANA). For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_ARRIVAL_TUNNEL_TYPE

The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by IANA. For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
     Windows SDK.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a>.


### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_ARRIVAL_INTERFACE_PROFILE_ID

The profile identifier (network category) of the arrival interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_INTERFACE_QUARANTINE_EPOCH

The time that has passed since the last media state change occurred for the network interface.
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_INBOUND_ICMP_ERROR_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks
The following macros in 
    <i>Fwpsk.h</i> are defined with FWPS_FIELDS_INBOUND_ICMP_ERROR_V6 enumeration
    values:

These macros are used to access the following IPV6 data fields:



The index of the local network interface, as enumerated by the network stack.

The index of the logical network interface, as enumerated by the network stack.

The type of the local network interface, as defined by the Internet Assigned Numbers Authority
       (IANA). For more information, see 
       <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
       Windows SDK.

The encapsulation method used by a tunnel if the IfType member of the IP_ADAPTER_ADDRESSES
       structure is IF_TYPE_TUNNEL. The tunnel type is defined by IANA. For more information, see 
       <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
       Windows SDK.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Unless otherwise noted, supported starting with Windows 7.

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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20FWPS_FIELDS_INBOUND_ICMP_ERROR_V6 enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

