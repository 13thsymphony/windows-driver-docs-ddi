---
UID: NE:fwpsk.FWPS_FIELDS_OUTBOUND_TRANSPORT_V6_
title: FWPS_FIELDS_OUTBOUND_TRANSPORT_V6_
author: windows-driver-content
description: The FWPS_FIELDS_OUTBOUND_TRANSPORT_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_OUTBOUND_TRANSPORT_V6 and FWPS_LAYER_OUTBOUND_TRANSPORT_V6_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_outbound_transport_v6.htm
old-project: netvista
ms.assetid: 7c9f5a23-06af-4538-8d2a-307500d61536
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_MAX, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_PROFILE_ID, fwpsk/FWPS_FIELDS_OUTBOUND_TRANSPORT_V6, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_INTERFACE_TYPE, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_DESTINATION_ADDRESS_TYPE, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_FLAGS, FWPS_FIELDS_OUTBOUND_TRANSPORT_V6 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELD_OUTBOUND_TRANSPORT_V6_PROFILE_ID, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_INTERFACE, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_REMOTE_PORT, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_TUNNEL_TYPE, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_MAX, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_PORT, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_PROTOCOL, netvista.fwps_fields_outbound_transport_v6, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_INTERFACE_INDEX, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_INTERFACE_TYPE, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_PORT, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_PROTOCOL, FWPS_FIELDS_OUTBOUND_TRANSPORT_V6_, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_TUNNEL_TYPE, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_REMOTE_ADDRESS, wfp_ref_5_const_3_data_fields_0ed53b16-48f2-4d6b-a64c-c6b966864542.xml, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_SUB_INTERFACE_INDEX, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_ADDRESS, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_INTERFACE_INDEX, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_SUB_INTERFACE_INDEX, FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_DESTINATION_ADDRESS_TYPE, FWPS_FIELDS_OUTBOUND_TRANSPORT_V6, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_FLAGS, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_REMOTE_PORT, fwpsk/FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_ADDRESS
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fwpsk.h
apiname:
-	FWPS_FIELDS_OUTBOUND_TRANSPORT_V6
product: Windows
targetos: Windows
req.typenames: FWPS_FIELDS_OUTBOUND_TRANSPORT_V6
---

# FWPS_FIELDS_OUTBOUND_TRANSPORT_V6_ Enumeration
The FWPS_FIELDS_OUTBOUND_TRANSPORT_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_OUTBOUND_TRANSPORT_V6 and FWPS_LAYER_OUTBOUND_TRANSPORT_V6_DISCARD 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layers</a>.

## Syntax
````
typedef enum FWPS_FIELDS_OUTBOUND_TRANSPORT_V6_ { 
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_PROTOCOL,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_ADDRESS,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_ADDRESS_TYPE,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_REMOTE_ADDRESS,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_PORT,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_REMOTE_PORT,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_INTERFACE,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_INTERFACE_INDEX,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_SUB_INTERFACE_INDEX,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_DESTINATION_ADDRESS_TYPE,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_FLAGS,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_INTERFACE_TYPE,
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_TUNNEL_TYPE,
#if (NTDDI_VERSION >= NTDDI_WIN7)
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_PROFILE_ID,
#endif 
  FWPS_FIELD_OUTBOUND_TRANSPORT_V6_MAX
} FWPS_FIELDS_OUTBOUND_TRANSPORT_V6;
````

## Constants

<table>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_COMPARTMENT_ID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_FLAGS</td>
                    <td>A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a>.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_INTERFACE_INDEX</td>
                    <td>The index of the network interface, as enumerated by the network stack.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_INTERFACE_TYPE</td>
                    <td>The type of the network interface, as defined by the Internet Assigned Numbers Authority (IANA).
     For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_DESTINATION_ADDRESS_TYPE</td>
                    <td>The destination IP address type. The possible values are defined by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a> enumeration.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_ADDRESS</td>
                    <td>The local IP address.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_ADDRESS_TYPE</td>
                    <td>The local IP address type. The possible values are defined by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a> enumeration.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_INTERFACE</td>
                    <td>The locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>) for the network interface associated with the
     local IP address.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_PORT</td>
                    <td>The local transport protocol port number.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_PROTOCOL</td>
                    <td>The IP protocol number, as specified in RFC 1700.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_REMOTE_ADDRESS</td>
                    <td>The remote IP address.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_REMOTE_PORT</td>
                    <td>The remote transport protocol port number.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IPSEC_SECURITY_REALM_ID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_MAX</td>
                    <td>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_PROFILE_ID</td>
                    <td>The profile identifier (network category) of the network interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div></td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_SUB_INTERFACE_INDEX</td>
                    <td>The index of the logical network interface, as enumerated by the network stack.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_TRANSPORT_V6_TUNNEL_TYPE</td>
                    <td>The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by IANA. For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
     Windows SDK.</td>
                </tr>
</table>

## Remarks

The following macros in 
    <i>Fwpsk.h</i> are defined with FWPS_FIELDS_OUTBOUND_TRANSPORT_V6 enumeration
    values:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
#define FWPS_FIELD_OUTBOUND_TRANSPORT_V6_ICMP_TYPE \
        FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_LOCAL_PORT

#define FWPS_FIELD_OUTBOUND_TRANSPORT_V6_ICMP_CODE \
        FWPS_FIELD_OUTBOUND_TRANSPORT_V6_IP_REMOTE_PORT
</pre>
</td>
</tr>
</table></span></div>
These macros are used to access the following IPV4 data fields:

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Unless otherwise noted, supported starting with Windows Vista. Unless otherwise noted, supported starting with Windows Vista. |
| **Header** | fwpsk.h (include Fwpsk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a>



<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_FIELDS_OUTBOUND_TRANSPORT_V6 enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>