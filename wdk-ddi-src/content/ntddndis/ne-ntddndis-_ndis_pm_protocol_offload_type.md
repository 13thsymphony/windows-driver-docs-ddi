---
UID : NE:ntddndis._NDIS_PM_PROTOCOL_OFFLOAD_TYPE
title : "_NDIS_PM_PROTOCOL_OFFLOAD_TYPE"
author : windows-driver-content
description : The NDIS_PM_PROTOCOL_OFFLOAD_TYPE enumeration identifies the type of a protocol offload for NDIS network adapter power management.
old-location : netvista\ndis_pm_protocol_offload_type.htm
old-project : netvista
ms.assetid : ab9f98d3-1792-43be-b838-f9dd3953889c
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : "*PNDIS_PM_PROTOCOL_OFFLOAD_TYPE, ntddndis/NdisPMProtocolOffloadIdMaximum, ntddndis/NdisPMProtocolOffload80211RSNRekey, NDIS_PM_PROTOCOL_OFFLOAD_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisPMProtocolOffloadIdUnspecified, PNDIS_PM_PROTOCOL_OFFLOAD_TYPE, NDIS_PM_PROTOCOL_OFFLOAD_TYPE, miniport_power_management_ref_5fcdc741-9efa-48ff-8b03-017859bf80c0.xml, ntddndis/NdisPMProtocolOffloadIdUnspecified, ntddndis/NdisPMProtocolOffloadIdIPv4ARP, NdisPMProtocolOffload80211RSNRekey, PNDIS_PM_PROTOCOL_OFFLOAD_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], ntddndis/NdisPMProtocolOffloadIdIPv6NS, _NDIS_PM_PROTOCOL_OFFLOAD_TYPE, NdisPMProtocolOffloadIdIPv6NS, ntddndis/PNDIS_PM_PROTOCOL_OFFLOAD_TYPE, ntddndis/NDIS_PM_PROTOCOL_OFFLOAD_TYPE, netvista.ndis_pm_protocol_offload_type, NdisPMProtocolOffloadIdIPv4ARP, NdisPMProtocolOffloadIdMaximum"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddndis.h
req.include-header : Ntddndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.20 and later.
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_PM_PROTOCOL_OFFLOAD_TYPE, NDIS_PM_PROTOCOL_OFFLOAD_TYPE"
---

# _NDIS_PM_PROTOCOL_OFFLOAD_TYPE Enumeration
The <b>NDIS_PM_PROTOCOL_OFFLOAD_TYPE</b> enumeration identifies the type of a protocol offload for NDIS
  network adapter power management.

## Syntax
````
typedef enum _NDIS_PM_PROTOCOL_OFFLOAD_TYPE { 
  NdisPMProtocolOffloadIdUnspecified,
  NdisPMProtocolOffloadIdIPv4ARP,
  NdisPMProtocolOffloadIdIPv6NS,
  NdisPMProtocolOffload80211RSNRekey,
  NdisPMProtocolOffloadIdMaximum
} NDIS_PM_PROTOCOL_OFFLOAD_TYPE, *PNDIS_PM_PROTOCOL_OFFLOAD_TYPE;
````

## Constants

<table>

<tr>
<td>NdisPMProtocolOffload80211RSNRekey</td>
<td>An IEEE 802.11i Robust Security Network (RSN) 4-way and 2-way handshake protocol offload. This
     protocol offload type is specified in the 
     <b>Dot11RSNRekeyParameters</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_pm_protocol_offload.md">NDIS_PM_PROTOCOL_OFFLOAD</a> structure.</td>
</tr>

<tr>
<td>NdisPMProtocolOffloadIdIPv4ARP</td>
<td>An IPv4 ARP protocol offload. The parameters for this protocol offload type are specified in the 
     <b>IPv4ARPParameters</b> member of the 
     <mshelp:link keywords="netvista.ndis_pm_protocol_offload" tabindex="0"><b>
     NDIS_PM_PROTOCOL_OFFLOAD</b></mshelp:link> structure.</td>
</tr>

<tr>
<td>NdisPMProtocolOffloadIdIPv6NS</td>
<td>An IPv6 Neighbor Solicitation (NS) protocol offload. The parameters for this protocol offload type
     are specified in the 
     <b>IPv6NSParameters</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_pm_protocol_offload.md">NDIS_PM_PROTOCOL_OFFLOAD</a> structure.</td>
</tr>

<tr>
<td>NdisPMProtocolOffloadIdMaximum</td>
<td>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</td>
</tr>

<tr>
<td>NdisPMProtocolOffloadIdUnspecified</td>
<td>The offloaded protocol is not specified.</td>
</tr>
</table>

## Remarks

The <b>NDIS_PM_PROTOCOL_OFFLOAD_TYPE</b> enumeration is used in the 
    <b>ProtocolOffloadType</b> member of the 
    <mshelp:link keywords="netvista.ndis_pm_protocol_offload" tabindex="0"><b>
    NDIS_PM_PROTOCOL_OFFLOAD</b></mshelp:link> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ntddndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_pm_protocol_offload.md">NDIS_PM_PROTOCOL_OFFLOAD</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PM_PROTOCOL_OFFLOAD_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>