---
UID: NS.NTDDNDIS._NDIS_ISOLATION_NAME
title: _NDIS_ISOLATION_NAME
author: windows-driver-content
description: The NDIS_ISOLATION_NAME structure contains an NDIS isolation name for a VM network adapter.
old-location: netvista\ndis_isolation_name.htm
old-project: NetVista
ms.assetid: 4712F853-8819-476C-8AD9-426EA5A0802E
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_ISOLATION_NAME, NDIS_ISOLATION_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.40 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_ISOLATION_NAME
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

# _NDIS_ISOLATION_NAME structure



## -description
The <b>NDIS_ISOLATION_NAME</b> structure contains an NDIS isolation name for a VM network adapter. The isolation name can be an isolation ID name or a routing domain name. This structure supports the following derived types:<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NDIS_ISOLATION_NAME NDIS_ISOLATION_ID_NAME, *PNDIS_ISOLATION_ID_NAME;
typedef NDIS_ISOLATION_NAME NDIS_ROUTING_DOMAIN_NAME, *PNDIS_ROUTING_DOMAIN_NAME;
</pre>
</td>
</tr>
</table></span></div>




## -syntax

````
typedef NDIS_ISOLATION_NAME NDIS_ISOLATION_ID_NAME, *PNDIS_ISOLATION_ID_NAME;
typedef NDIS_ISOLATION_NAME NDIS_ROUTING_DOMAIN_NAME, *PNDIS_ROUTING_DOMAIN_NAME;

````


## -struct-fields

### -field Length

Length, in bytes, of the NDIS isolation name. This member must be less than or equal to <b>NDIS_ISOLATION_NAME_MAX_STRING_SIZE</b>.


### -field        String

A <b>NULL</b>-terminated string that contains the NDIS isolation name. The isolation name can be an isolation ID name or a routing domain name.


## -remarks
This structure is used in:<ul>
<li>
The <b>IsolationIdName</b> member of the <a href="netvista.ndis_routing_domain_isolation_entry">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a> structure.

</li>
<li>
The <b>RoutingDomainName</b> member of the <a href="netvista.ndis_routing_domain_entry">NDIS_ROUTING_DOMAIN_ENTRY</a> structure.

</li>
<li>
The <b>RoutingDomainName</b> member of the <a href="netvista.ndis_switch_port_property_routing_domain">NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</a> structure.

</li>
</ul>


The <b>IsolationIdName</b> member of the <a href="netvista.ndis_routing_domain_isolation_entry">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a> structure.

The <b>RoutingDomainName</b> member of the <a href="netvista.ndis_routing_domain_entry">NDIS_ROUTING_DOMAIN_ENTRY</a> structure.

The <b>RoutingDomainName</b> member of the <a href="netvista.ndis_switch_port_property_routing_domain">NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</a> structure.


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
<a href="netvista.ndis_isolation_mode">NDIS_ISOLATION_MODE</a>
</dt>
<dt>
<a href="netvista.ndis_routing_domain_entry">NDIS_ROUTING_DOMAIN_ENTRY</a>
</dt>
<dt>
<a href="netvista.ndis_routing_domain_isolation_entry">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a>
</dt>
<dt>
<a href="netvista.ndis_switch_port_property_routing_domain">NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_ISOLATION_NAME structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

