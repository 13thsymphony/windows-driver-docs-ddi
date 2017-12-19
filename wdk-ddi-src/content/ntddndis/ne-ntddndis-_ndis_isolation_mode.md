---
UID: NE.ntddndis._NDIS_ISOLATION_MODE
title: _NDIS_ISOLATION_MODE
author: windows-driver-content
description: The NDIS_ISOLATION_MODE enumeration defines the network isolation modes that can be specified for a VM network adapter.
old-location: netvista\ndis_isolation_mode.htm
old-project: NetVista
ms.assetid: DA4765CD-808C-438A-9CA6-5ADC27A70EC8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_ISOLATION_MODE, PNDIS_ISOLATION_MODE, *PNDIS_ISOLATION_MODE, NDIS_ISOLATION_MODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.40 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_ISOLATION_MODE
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

# _NDIS_ISOLATION_MODE enumeration



## -description
The <b>NDIS_ISOLATION_MODE</b> enumeration defines the network isolation modes that can be specified for a VM network adapter.



## -syntax

````
typedef enum _NDIS_ISOLATION_MODE { 
  NdisIsolationModeNone                   = 0,
  NdisIsolationModeNativeVirtualSubnet    = 1,
  NdisIsolationModeExternalVirtualSubnet  = 2,
  NdisIsolationModeVlan                   = 3
} NDIS_ISOLATION_MODE;
````


## -enum-fields

### -field NdisIsolationModeNone

Network isolation is not supported.


### -field NdisIsolationModeNativeVirtualSubnet

Native <b>VirtualSubnetId</b>-based isolation provided by Hyper-V Network Virtualization.


### -field NdisIsolationModeExternalVirtualSubnet

External <b>VirtualSubnetId</b>-based isolation provided by a Hyper-V Extensible Switch extension.


### -field NdisIsolationModeVlan

Virtual local area network (VLAN)-based isolation.


## -remarks
<b>NDIS_ISOLATION_MODE</b> enumeration values are used in the <b>IsolationMode</b> member of the <a href="netvista.ndis_isolation_parameters">NDIS_ISOLATION_PARAMETERS</a> and <a href="netvista.ndis_switch_port_property_isolation">NDIS_SWITCH_PORT_PROPERTY_ISOLATION</a> structures.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.40 and later.

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
<dt>
<a href="netvista.ndis_isolation_parameters">NDIS_ISOLATION_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndis_switch_port_property_isolation">NDIS_SWITCH_PORT_PROPERTY_ISOLATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_ISOLATION_MODE enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

