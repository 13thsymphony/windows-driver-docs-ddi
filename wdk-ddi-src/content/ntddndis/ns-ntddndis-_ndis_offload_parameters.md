---
UID : NS:ntddndis._NDIS_OFFLOAD_PARAMETERS
title : "_NDIS_OFFLOAD_PARAMETERS"
author : windows-driver-content
description : The NDIS_OFFLOAD_PARAMETERS structure specifies the current task offload configuration settings in response to an OID set request of OID_TCP_OFFLOAD_PARAMETERS.
old-location : netvista\ndis_offload_parameters.htm
old-project : netvista
ms.assetid : ceb6647a-a43e-4ab1-88d4-49927103ecba
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : tcpip_offload_ref_9ae50974-12a7-4c63-973e-27684a4f1474.xml, NDIS_OFFLOAD_PARAMETERS structure [Network Drivers Starting with Windows Vista], NDIS_OFFLOAD_SET_ON, NDIS_OFFLOAD_PARAMETERS_IPSECV1_ESP_ENABLED, NDIS_OFFLOAD_PARAMETERS_REVISION_1, NDIS_OFFLOAD_PARAMETERS_RSC_DISABLED, *PNDIS_OFFLOAD_PARAMETERS, NDIS_OFFLOAD_PARAMETERS_NO_CHANGE, NDIS_OFFLOAD_PARAMETERS_IPSECV1_AH_AND_ESP_ENABLED, NDIS_OFFLOAD_PARAMETERS_IPSECV2_ESP_ENABLED, NDIS_OFFLOAD_PARAMETERS_RSC_ENABLED, netvista.ndis_offload_parameters, NDIS_OFFLOAD_SET_NO_CHANGE, NDIS_OFFLOAD_PARAMETERS_LSOV1_DISABLED, PNDIS_OFFLOAD_PARAMETERS, NDIS_OFFLOAD_PARAMETERS_IPSECV1_DISABLED, NDIS_OFFLOAD_PARAMETERS_REVISION_3, NDIS_OFFLOAD_PARAMETERS_LSOV1_ENABLED, NDIS_OFFLOAD_PARAMETERS_LSOV2_DISABLED, NDIS_OFFLOAD_PARAMETERS_REVISION_2, NDIS_OFFLOAD_PARAMETERS_LSOV2_ENABLED, _NDIS_OFFLOAD_PARAMETERS, NDIS_OFFLOAD_PARAMETERS, NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_AND_ESP_ENABLED, PNDIS_OFFLOAD_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], ntddndis/PNDIS_OFFLOAD_PARAMETERS, NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_ENABLED, ntddndis/NDIS_OFFLOAD_PARAMETERS, NDIS_OFFLOAD_PARAMETERS_IPSECV2_DISABLED, NDIS_ENCAPSULATION_TYPE_GRE_MAC, NDIS_OFFLOAD_SET_OFF, NDIS_OFFLOAD_PARAMETERS_IPSECV1_AH_ENABLED
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Windows Vista,Supported in NDIS 6.0 and later.
req.target-min-winversvr : Windows Server 2008
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_OFFLOAD_PARAMETERS, NDIS_OFFLOAD_PARAMETERS"
---

# _NDIS_OFFLOAD_PARAMETERS structure
The <b>NDIS_OFFLOAD_PARAMETERS</b> structure specifies the current task offload configuration settings in
  response to an 
  OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569807">OID_TCP_OFFLOAD_PARAMETERS</a>.

## Syntax
````
typedef struct _NDIS_OFFLOAD_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  UCHAR              IPv4Checksum;
  UCHAR              TCPIPv4Checksum;
  UCHAR              UDPIPv4Checksum;
  UCHAR              TCPIPv6Checksum;
  UCHAR              UDPIPv6Checksum;
  UCHAR              LsoV1;
  UCHAR              IPsecV1;
  UCHAR              LsoV2IPv4;
  UCHAR              LsoV2IPv6;
  UCHAR              TcpConnectionIPv4;
  UCHAR              TcpConnectionIPv6;
  ULONG              Flags;
#if (NDIS_SUPPORT_NDIS61)
  UCHAR              IPsecV2;
  UCHAR              IPsecV2IPv4;
#endif 
#if (NDIS_SUPPORT_NDIS630)
  struct {
    UCHAR RscIPv4;
    UCHAR RscIPv6;
  };
#endif 
#if (NDIS_SUPPORT_NDIS630)
  struct {
    UCHAR EncapsulatedPacketTaskOffload;
    UCHAR EncapsulationTypes;
  };
#endif 
} NDIS_OFFLOAD_PARAMETERS, *PNDIS_OFFLOAD_PARAMETERS;
````

## Members


`_ENCAPSULATION_PROTOCOL_PARAMETERS`



`EncapsulationProtocolParameters`



`Flags`

A set of flags that can be combined with a bitwise OR operation. Set this member to zero. There
     are currently no flags defined.

`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_OFFLOAD_PARAMETERS</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT.
     

To indicate the version of the <b>NDIS_OFFLOAD_PARAMETERS</b> structure, set the 
     <b>Revision</b> member to one of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_REVISION_3"></a><a id="ndis_offload_parameters_revision_3"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_REVISION_3</b></dt>
<dt>3</dt>
</dl>
</td>
<td width="60%">
Supports the 
        <b>RscIPv4</b> , <b>RscIPv6</b>, <b>EncapsulatedPacketTaskOffload</b>, and   <b>EncapsulationTypes</b> members for NDIS 6.30.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_OFFLOAD_PARAMETERS_REVISION_3.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_REVISION_2"></a><a id="ndis_offload_parameters_revision_2"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_REVISION_2</b></dt>
<dt>2</dt>
</dl>
</td>
<td width="60%">
Supports the 
        <b>IPsecV2</b>, 
        <b>IPsecV2IPv4</b>, 
        <b>Reserved1</b>, and 
        <b>Reserved2</b> members for NDIS 6.1.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_OFFLOAD_PARAMETERS_REVISION_2.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_REVISION_1"></a><a id="ndis_offload_parameters_revision_1"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_REVISION_1</b></dt>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Original version for NDIS 6.0.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_OFFLOAD_PARAMETERS_REVISION_1.

</td>
</tr>
</table>

`IPsecV1`

The Internet protocol security (IPsec) offload setting of the miniport adapter. This setting
     should be one of the following values:
     
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_NO_CHANGE"></a><a id="ndis_offload_parameters_no_change"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_NO_CHANGE</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver should not change the current setting.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_IPSECV1_DISABLED"></a><a id="ndis_offload_parameters_ipsecv1_disabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_IPSECV1_DISABLED</b></dt>
</dl>
</td>
<td width="60%">
IPsec offload is disabled.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_IPSECV1_AH_ENABLED"></a><a id="ndis_offload_parameters_ipsecv1_ah_enabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_IPSECV1_AH_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
The IPsec offload Authentication Header (AH) feature should be enabled for transmit and
       receive.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_IPSECV1_ESP_ENABLED"></a><a id="ndis_offload_parameters_ipsecv1_esp_enabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_IPSECV1_ESP_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
The IPsec offload Encapsulating Security Payload (ESP) feature should be enabled for transmit
       and receive.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_IPSECV1_AH_AND_ESP_ENABLED"></a><a id="ndis_offload_parameters_ipsecv1_ah_and_esp_enabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_IPSECV1_AH_AND_ESP_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
The IPsec offload AH and ESP features areenabled for transmit and receive.

</td>
</tr>
</table>

`IPsecV2`

The Internet protocol security (IPsec) offload version 2 setting of a miniport adapter that supports
      IPv6 and IPv4. This member specifies the setting for both IPv6 and IPv4 support. This setting should be
      one of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_NO_CHANGE"></a><a id="ndis_offload_parameters_no_change"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_NO_CHANGE</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver should not change the current setting.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_IPSECV2_DISABLED"></a><a id="ndis_offload_parameters_ipsecv2_disabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_IPSECV2_DISABLED</b></dt>
</dl>
</td>
<td width="60%">
IPsec offload version 2 is disabled.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_ENABLED"></a><a id="ndis_offload_parameters_ipsecv2_ah_enabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
The IPsec offload version 2 Authentication Header (AH) feature should be enabled for transmit
        and receive.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_IPSECV2_ESP_ENABLED"></a><a id="ndis_offload_parameters_ipsecv2_esp_enabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_IPSECV2_ESP_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
The IPsec offload version 2 Encapsulating Security Payload (ESP) feature should be enabled for
        transmit and receive.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_AND_ESP_ENABLED"></a><a id="ndis_offload_parameters_ipsecv2_ah_and_esp_enabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_AND_ESP_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
The IPsec offload version 2A H and ESP features are enabled for transmit and receive.

</td>
</tr>
</table>

`IPsecV2IPv4`

The Internet protocol security (IPsec) offload version 2 setting of a miniport adapter that supports
      IPv4 and does not support IPv6. If the miniport driver supports IPv6, the 
      <b>IPsecV2</b> member specifies the IPv4 setting and this member is not used. This setting should be one
      of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_NO_CHANGE"></a><a id="ndis_offload_parameters_no_change"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_NO_CHANGE</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver should not change the current setting.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_IPSECV2_DISABLED"></a><a id="ndis_offload_parameters_ipsecv2_disabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_IPSECV2_DISABLED</b></dt>
</dl>
</td>
<td width="60%">
IPsec offload version 2 is disabled.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_ENABLED"></a><a id="ndis_offload_parameters_ipsecv2_ah_enabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
The IPsec offload version 2 Authentication Header (AH) feature should be enabled for transmit
        and receive.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_IPSECV2_ESP_ENABLED"></a><a id="ndis_offload_parameters_ipsecv2_esp_enabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_IPSECV2_ESP_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
The IPsec offload version 2 Encapsulating Security Payload (ESP) feature should be enabled for
        transmit and receive.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_AND_ESP_ENABLED"></a><a id="ndis_offload_parameters_ipsecv2_ah_and_esp_enabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_AND_ESP_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
The IPsec offload version 2A H and ESP features are enabled for transmit and receive.

</td>
</tr>
</table>

`IPv4Checksum`

The IPv4 checksum setting of the miniport adapter. For more information, see the following Remarks
     section.

`LsoV1`

The large send offload version 1 (LSOV1) setting of the miniport adapter. This setting should be
     one of the following values:
     
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_NO_CHANGE"></a><a id="ndis_offload_parameters_no_change"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_NO_CHANGE</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver should not change the current setting.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_LSOV1_DISABLED"></a><a id="ndis_offload_parameters_lsov1_disabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_LSOV1_DISABLED</b></dt>
</dl>
</td>
<td width="60%">
LSOV1 is disabled.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_LSOV1_ENABLED"></a><a id="ndis_offload_parameters_lsov1_enabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_LSOV1_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
LSOV1 is enabled.

</td>
</tr>
</table>

`LsoV2IPv4`

The IPv4 large send offload version 2 (LSOV2) setting of the miniport adapter. This setting should
     be one of the following values:
     
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_NO_CHANGE"></a><a id="ndis_offload_parameters_no_change"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_NO_CHANGE</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver should not change the current setting.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_LSOV2_DISABLED"></a><a id="ndis_offload_parameters_lsov2_disabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_LSOV2_DISABLED</b></dt>
</dl>
</td>
<td width="60%">
LSOV2 for IPv4 is disabled.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_LSOV2_ENABLED"></a><a id="ndis_offload_parameters_lsov2_enabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_LSOV2_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
LSOV2 for IPv4 is enabled.

</td>
</tr>
</table>

`LsoV2IPv6`

The IPv6 LSOV2 setting of the miniport adapter. These settings are specified as one of the
     following values:
     
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_NO_CHANGE"></a><a id="ndis_offload_parameters_no_change"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_NO_CHANGE</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver should not change the current setting.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_LSOV2_DISABLED"></a><a id="ndis_offload_parameters_lsov2_disabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_LSOV2_DISABLED</b></dt>
</dl>
</td>
<td width="60%">
LSOV2 for IPv6 is disabled.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_LSOV2_ENABLED"></a><a id="ndis_offload_parameters_lsov2_enabled"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_LSOV2_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
LSOV2 for IPv6 is enabled.

</td>
</tr>
</table>

`TcpConnectionIPv4`

The IPv4 connection offload setting of the miniport adapter. These settings are specified as one
     of the following values:
     
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_NO_CHANGE"></a><a id="ndis_offload_parameters_no_change"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_NO_CHANGE</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver should not change the current setting.

</td>
</tr>
</table>

`TcpConnectionIPv6`

The IPv6 connection offload setting of the miniport adapter. These settings are specified as one
     of the following values:
     
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_OFFLOAD_PARAMETERS_NO_CHANGE"></a><a id="ndis_offload_parameters_no_change"></a><dl>
<dt><b>NDIS_OFFLOAD_PARAMETERS_NO_CHANGE</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver should not change the current setting.

</td>
</tr>
</table>

`TCPIPv4Checksum`

The IPv4 checksum setting of the miniport adapter for TCP packets. For more information, see the
     following Remarks section.

`TCPIPv6Checksum`

The IPv6 checksum setting of the miniport adapter for TCP packets. For more information, see the
     following Remarks section.

`UDPIPv4Checksum`

The IPv4 checksum setting of the miniport adapter for UDP packets. For more information, see the
     following Remarks section.

`UDPIPv6Checksum`

The IPv6 checksum setting of the miniport adapter for UDP packets. For more information, see the
     following Remarks section.

## Remarks
In response to an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569807">OID_TCP_OFFLOAD_PARAMETERS</a> OID set
    request, a miniport driver uses the settings in the <b>NDIS_OFFLOAD_PARAMETERS</b> structure to set the current
    configuration of the miniport adapter.

NDIS retains the requested settings in the registry in the offload standardized keywords. When NDIS
    restarts the miniport adapter, the miniport driver reads the offload standardized keywords and uses them
    to set the default offload configuration of the NIC.

To access the checksum offload settings, use the following members of the <b>NDIS_OFFLOAD_PARAMETERS</b>
    structure:

<b>IPv4Checksum</b>

<b>TCPIPv4Checksum</b>

<b>UDPIPv4Checksum</b>

<b>TCPIPv6Checksum</b>

<b>UDPIPv6Checksum</b>

The preceding members can have one of the following values:

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569807">OID_TCP_OFFLOAD_PARAMETERS</a>

<mshelp:link keywords="netvista.oid_tcp_offload_hardware_capabilities" tabindex="0">
   OID_TCP_OFFLOAD_HARDWARE_CAPABILITIES</mshelp:link>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_OFFLOAD_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>