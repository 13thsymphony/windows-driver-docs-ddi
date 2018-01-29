---
UID : NE:ntddndis._NDIS_ISOLATION_MODE
title : _NDIS_ISOLATION_MODE
author : windows-driver-content
description : The NDIS_ISOLATION_MODE enumeration defines the network isolation modes that can be specified for a VM network adapter.
old-location : netvista\ndis_isolation_mode.htm
old-project : netvista
ms.assetid : DA4765CD-808C-438A-9CA6-5ADC27A70EC8
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddndis/NdisIsolationModeVlan, *PNDIS_ISOLATION_MODE, NDIS_ISOLATION_MODE, ntddndis/NdisIsolationModeExternalVirtualSubnet, _NDIS_ISOLATION_MODE, NdisIsolationModeNativeVirtualSubnet, NDIS_ISOLATION_MODE enumeration [Network Drivers Starting with Windows Vista], ntddndis/NDIS_ISOLATION_MODE, netvista.ndis_isolation_mode, NdisIsolationModeNone, NdisIsolationModeVlan, ntddndis/NdisIsolationModeNone, ntddndis/NdisIsolationModeNativeVirtualSubnet, NdisIsolationModeExternalVirtualSubnet
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.40 and later.
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
req.typenames : NDIS_ISOLATION_MODE, *PNDIS_ISOLATION_MODE
---

# _NDIS_ISOLATION_MODE Enumeration
The <b>NDIS_ISOLATION_MODE</b> enumeration defines the network isolation modes that can be specified for a VM network adapter.

## Syntax
````
typedef enum _NDIS_ISOLATION_MODE { 
  NdisIsolationModeNone                   = 0,
  NdisIsolationModeNativeVirtualSubnet    = 1,
  NdisIsolationModeExternalVirtualSubnet  = 2,
  NdisIsolationModeVlan                   = 3
} NDIS_ISOLATION_MODE;
````

## Constants

<table>

<tr>
<td>NdisIsolationModeExternalVirtualSubnet</td>
<td>External <b>VirtualSubnetId</b>-based isolation provided by a Hyper-V Extensible Switch extension.</td>
</tr>

<tr>
<td>NdisIsolationModeNativeVirtualSubnet</td>
<td>Native <b>VirtualSubnetId</b>-based isolation provided by Hyper-V Network Virtualization.</td>
</tr>

<tr>
<td>NdisIsolationModeNone</td>
<td>Network isolation is not supported.</td>
</tr>

<tr>
<td>NdisIsolationModeVlan</td>
<td>Virtual local area network (VLAN)-based isolation.</td>
</tr>
</table>

## Remarks

<b>NDIS_ISOLATION_MODE</b> enumeration values are used in the <b>IsolationMode</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_isolation_parameters.md">NDIS_ISOLATION_PARAMETERS</a> and <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_isolation.md">NDIS_SWITCH_PORT_PROPERTY_ISOLATION</a> structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_isolation.md">NDIS_SWITCH_PORT_PROPERTY_ISOLATION</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_isolation_parameters.md">NDIS_ISOLATION_PARAMETERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_ISOLATION_MODE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>