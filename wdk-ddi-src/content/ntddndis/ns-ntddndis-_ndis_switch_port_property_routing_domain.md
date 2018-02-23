---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN
title: "_NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure is used to specify the routing domain properties of a VM network adapter.
old-location: netvista\ndis_switch_port_property_routing_domain.htm
old-project: netvista
ms.assetid: 6E1DF4F3-9ED4-4E34-A768-1B5008D61B0C
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure [Network Drivers Starting with Windows Vista], ntddndis/PNDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN, *PNDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN, ntddndis/NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN, PNDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure pointer [Network Drivers Starting with Windows Vista], NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN, _NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN, netvista.ndis_switch_port_property_routing_domain, PNDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN, NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN"
---

# _NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure
The <b>NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</b> structure is used to specify the routing domain properties of a VM network adapter.

## Syntax
````
typedef struct _NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN {
  NDIS_OBJECT_HEADER       Header;
  ULONG                    Flags;
  NDIS_ROUTING_DOMAIN_ID   RoutingDomainId;
  NDIS_ROUTING_DOMAIN_NAME RoutingDomainName;
  ULONG {
    USHORT FirstIsolationEntryOffset;
  }                   NumIsolationEntries;
} NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN, *PNDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN;
````

## Members


`FirstIsolationEntryOffset`



`Flags`

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

`Header`

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</b>  structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN_REVISION_1

Original version for NDIS 6.40 and later.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN_REVISION_1</b>.

`NumIsolationEntries`

A <b>ULONG</b> value that specifies the number of <a href="..\ntddndis\ns-ntddndis-_ndis_routing_domain_isolation_entry.md">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a> in the array that follows the <b>NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</b> structure.



#### FirstIsolationEntryOffset

The offset, in bytes, from the beginning of the buffer pointed to by the <b>InformationBuffer</b> member of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure to the first isolation entry.

`RoutingDomainId`

The routing domain identifier for the VM network adapter. This identifier is a GUID.

`RoutingDomainName`

An <a href="..\ntddndis\ns-ntddndis-_ndis_isolation_name.md">NDIS_ISOLATION_NAME</a> structure that contains the routing domain name for the VM network adapter.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.40 and later. Supported in NDIS 6.40 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_routing_domain_isolation_entry.md">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598256">NDIS_SWITCH_PROPERTY_PARAMETERS_GET_PROPERTY</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_routing_domain_entry.md">NDIS_ROUTING_DOMAIN_ENTRY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>