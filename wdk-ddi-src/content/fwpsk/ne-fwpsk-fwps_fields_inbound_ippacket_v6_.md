---
UID : NE:fwpsk.FWPS_FIELDS_INBOUND_IPPACKET_V6_
title : FWPS_FIELDS_INBOUND_IPPACKET_V6_
author : windows-driver-content
description : The FWPS_FIELDS_INBOUND_IPPACKET_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_INBOUND_IPPACKET_V6 and FWPS_LAYER_INBOUND_IPPACKET_V6_DISCARD run-time filtering layers.
old-location : netvista\fwps_fields_inbound_ippacket_v6.htm
old-project : netvista
ms.assetid : 764cee8d-d690-4d31-a6fc-677419513a15
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_TYPE, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_FLAGS, FWPS_FIELDS_INBOUND_IPPACKET_V6 enumeration [Network Drivers Starting with Windows Vista], fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_INDEX, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_TYPE, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_MAX, FWPS_FIELD_INBOUND_IPPACKET_V6_TUNNEL_TYPE, fwpsk/FWPS_FIELDS_INBOUND_IPPACKET_V6, FWPS_FIELD_INBOUND_IPPACKET_V6_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_SUB_INTERFACE_INDEX, FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_IP_REMOTE_ADDRESS, FWPS_FIELD_INBOUND_IPPACKET_V6_SUB_INTERFACE_INDEX, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_TUNNEL_TYPE, FWPS_FIELDS_INBOUND_IPPACKET_V6_, FWPS_FIELDS_INBOUND_IPPACKET_V6, FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_INDEX, netvista.fwps_fields_inbound_ippacket_v6, FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS, wfp_ref_5_const_3_data_fields_7185d69a-4508-4b06-b2e3-edee65a7f8c0.xml, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS, FWPS_FIELD_INBOUND_IPPACKET_V6_FLAGS, FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_INTERFACE, FWPS_FIELD_INBOUND_IPPACKET_V6_MAX
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows Vista.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : FWPS_FIELDS_INBOUND_IPPACKET_V6
---

# FWPS_FIELDS_INBOUND_IPPACKET_V6_ Enumeration
The FWPS_FIELDS_INBOUND_IPPACKET_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_INBOUND_IPPACKET_V6 and FWPS_LAYER_INBOUND_IPPACKET_V6_DISCARD 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layers</a>.

## Syntax
````
typedef enum FWPS_FIELDS_INBOUND_IPPACKET_V6_ { 
  FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS,
  FWPS_FIELD_INBOUND_IPPACKET_V6_IP_REMOTE_ADDRESS,
  FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS_TYPE,
  FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_INTERFACE,
  FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_INDEX,
  FWPS_FIELD_INBOUND_IPPACKET_V6_SUB_INTERFACE_INDEX,
  FWPS_FIELD_INBOUND_IPPACKET_V6_FLAGS,
  FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_TYPE,
  FWPS_FIELD_INBOUND_IPPACKET_V6_TUNNEL_TYPE,
  FWPS_FIELD_INBOUND_IPPACKET_V6_MAX
} FWPS_FIELDS_INBOUND_IPPACKET_V6;
````

## Constants

<table>

<tr>
<td>FWPS_FIELD_INBOUND_IPPACKET_V6_COMPARTMENT_ID</td>
<td></td>
</tr>

<tr>
<td>FWPS_FIELD_INBOUND_IPPACKET_V6_FLAGS</td>
<td>A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a>.</td>
</tr>

<tr>
<td>FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_INDEX</td>
<td>The index of the network interface, as enumerated by the network stack.</td>
</tr>

<tr>
<td>FWPS_FIELD_INBOUND_IPPACKET_V6_INTERFACE_TYPE</td>
<td>The type of the network interface, as defined by the Internet Assigned Numbers Authority (IANA).
     For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.</td>
</tr>

<tr>
<td>FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS</td>
<td>The local IP address.</td>
</tr>

<tr>
<td>FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_ADDRESS_TYPE</td>
<td>The local IP address type. The possible values are defined by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a> enumeration</td>
</tr>

<tr>
<td>FWPS_FIELD_INBOUND_IPPACKET_V6_IP_LOCAL_INTERFACE</td>
<td>The locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>) for the network interface associated with the
     local IP address.</td>
</tr>

<tr>
<td>FWPS_FIELD_INBOUND_IPPACKET_V6_IP_REMOTE_ADDRESS</td>
<td>The remote IP address.</td>
</tr>

<tr>
<td>FWPS_FIELD_INBOUND_IPPACKET_V6_MAX</td>
<td>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</td>
</tr>

<tr>
<td>FWPS_FIELD_INBOUND_IPPACKET_V6_SUB_INTERFACE_INDEX</td>
<td>The index of the logical network interface, as enumerated by the network stack.</td>
</tr>

<tr>
<td>FWPS_FIELD_INBOUND_IPPACKET_V6_TUNNEL_TYPE</td>
<td>The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by IANA. For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
     Windows SDK.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fwpsk.h (include Fwpsk.h) |

## See Also

<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_FIELDS_INBOUND_IPPACKET_V6 enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>