---
UID : NE:fwpsk.FWPS_FIELDS_STREAM_PACKET_V6_
title : FWPS_FIELDS_STREAM_PACKET_V6_
author : windows-driver-content
description : The FWPS_FIELDS_STREAM_PACKET_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_STREAM_PACKET_V6 run-time filtering layer.
old-location : netvista\fwps_fields_stream_packet_v6.htm
old-project : netvista
ms.assetid : fa2a415d-11be-49f1-ad93-975c25f3db07
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : FWPS_FIELDS_STREAM_PACKET_V6_, FWPS_FIELDS_STREAM_PACKET_V6
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 7.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FWPS_FIELDS_STREAM_PACKET_V6
req.alt-loc : fwpsk.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= DISPATCH_LEVEL
req.typenames : FWPS_FIELDS_STREAM_PACKET_V6
---

# FWPS_FIELDS_STREAM_PACKET_V6_ Enumeration
The FWPS_FIELDS_STREAM_PACKET_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_STREAM_PACKET_V6 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layer</a>.

## Syntax
````
typedef enum FWPS_FIELDS_STREAM_PACKET_V6_ { 
  FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_ADDRESS,
  FWPS_FIELD_STREAM_PACKET_V6_IP_REMOTE_ADDRESS,
  FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_PORT,
  FWPS_FIELD_STREAM_PACKET_V6_IP_REMOTE_PORT,
  FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_INTERFACE,
  FWPS_FIELD_STREAM_PACKET_V6_INTERFACE_INDEX,
  FWPS_FIELD_STREAM_PACKET_V6_SUB_INTERFACE_INDEX,
  FWPS_FIELD_STREAM_PACKET_V6_DIRECTION,
  FWPS_FIELD_STREAM_PACKET_V6_FLAGS,
  FWPS_FIELD_STREAM_PACKET_V6_INTERFACE_TYPE,
  FWPS_FIELD_STREAM_PACKET_V6_TUNNEL_TYPE,
  FWPS_FIELD_STREAM_PACKET_V6_MAX
} FWPS_FIELDS_STREAM_PACKET_V6;
````

## Constants

<table>

<tr>
<td>FWPS_FIELD_STREAM_PACKET_V6_DIRECTION</td>
<td></td>
</tr>

<tr>
<td>FWPS_FIELD_STREAM_PACKET_V6_FLAGS</td>
<td>A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a>.</td>
</tr>

<tr>
<td>FWPS_FIELD_STREAM_PACKET_V6_INTERFACE_INDEX</td>
<td>The index of the network interface, as enumerated by the network stack.</td>
</tr>

<tr>
<td>FWPS_FIELD_STREAM_PACKET_V6_INTERFACE_TYPE</td>
<td>The type of the network interface, as defined by the Internet Assigned Numbers Authority (IANA).
     For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.</td>
</tr>

<tr>
<td>FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_ADDRESS</td>
<td>The local IP address.</td>
</tr>

<tr>
<td>FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_INTERFACE</td>
<td>The locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>) for the network interface associated with the
     local IP address.</td>
</tr>

<tr>
<td>FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_PORT</td>
<td>The local transport protocol port number.</td>
</tr>

<tr>
<td>FWPS_FIELD_STREAM_PACKET_V6_IP_REMOTE_ADDRESS</td>
<td>The remote IP address.</td>
</tr>

<tr>
<td>FWPS_FIELD_STREAM_PACKET_V6_IP_REMOTE_PORT</td>
<td>The remote transport protocol port number.</td>
</tr>

<tr>
<td>FWPS_FIELD_STREAM_PACKET_V6_MAX</td>
<td>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</td>
</tr>

<tr>
<td>FWPS_FIELD_STREAM_PACKET_V6_SUB_INTERFACE_INDEX</td>
<td>The index of the logical network interface, as enumerated by the network stack.</td>
</tr>

<tr>
<td>FWPS_FIELD_STREAM_PACKET_V6_TUNNEL_TYPE</td>
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

<dl>
<dt>
<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_FIELDS_STREAM_PACKET_V6 enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>