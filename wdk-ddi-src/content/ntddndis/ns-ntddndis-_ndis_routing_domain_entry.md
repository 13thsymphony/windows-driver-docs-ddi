---
UID: NS:ntddndis._NDIS_ROUTING_DOMAIN_ENTRY
title: "_NDIS_ROUTING_DOMAIN_ENTRY"
author: windows-driver-content
description: The NDIS_ROUTING_DOMAIN_ENTRY structure is used by the OID_GEN_ISOLATION_PARAMETERS OID to return the routing domain entries for a VM network adapter's port.
old-location: netvista\ndis_routing_domain_entry.htm
old-project: netvista
ms.assetid: 65E39285-AFD2-4098-A983-C7FA06505407
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_ROUTING_DOMAIN_ENTRY, NDIS_ROUTING_DOMAIN_ENTRY, NDIS_ROUTING_DOMAIN_ENTRY structure [Network Drivers Starting with Windows Vista], PNDIS_ROUTING_DOMAIN_ENTRY, PNDIS_ROUTING_DOMAIN_ENTRY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_ROUTING_DOMAIN_ENTRY, netvista.ndis_routing_domain_entry, ntddndis/NDIS_ROUTING_DOMAIN_ENTRY, ntddndis/PNDIS_ROUTING_DOMAIN_ENTRY"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_ROUTING_DOMAIN_ENTRY
product: Windows
targetos: Windows
req.typenames: NDIS_ROUTING_DOMAIN_ENTRY, *PNDIS_ROUTING_DOMAIN_ENTRY
---

# _NDIS_ROUTING_DOMAIN_ENTRY structure
The <b>NDIS_ROUTING_DOMAIN_ENTRY</b> structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn383690">OID_GEN_ISOLATION_PARAMETERS</a> OID to return the routing domain entries for a VM network adapter's port.

## Syntax
````
typedef struct _NDIS_ROUTING_DOMAIN_ENTRY {
  NDIS_OBJECT_HEADER       Header;
  ULONG                    Flags;
  NDIS_ROUTING_DOMAIN_ID   RoutingDomainId;
  NDIS_ROUTING_DOMAIN_NAME RoutingDomainName;
  ULONG                    NumIsolationEntries;
  ULONG                    FirstIsolationEntryOffset;
} NDIS_ROUTING_DOMAIN_ENTRY, *PNDIS_ROUTING_DOMAIN_ENTRY;
````

## Members


`FirstIsolationEntryOffset`

A <b>ULONG</b> value that specifies the offset, in bytes, to the first <b>NDIS_ROUTING_DOMAIN_ENTRY</b> element in the array that follows the <a href="..\ntddndis\ns-ntddndis-_ndis_isolation_parameters.md">NDIS_ISOLATION_PARAMETERS</a> structure in the buffer that the <b>InformationBuffer</b> member of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure points to. The offset is measured from the start of the <b>NDIS_ROUTING_DOMAIN_ENTRY</b> structure to the beginning of the first element of the array.

<div class="alert"><b>Note</b>  If the value of <b>NumRoutingDomainEntries</b> is zero, this member is ignored.</div>
<div> </div>

`Flags`

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

`Header`

The type, revision, and size of the <b>NDIS_ROUTING_DOMAIN_ENTRY</b>  structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>. To specify the version of the <b>NDIS_ROUTING_DOMAIN_ENTRY</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_ROUTING_DOMAIN_ENTRY_REVISION_1

Original version for NDIS 6.40 and later.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_ROUTING_DOMAIN_ENTRY_REVISION_1</b>.

`NumIsolationEntries`

A <b>ULONG</b> value that specifies the number of <a href="..\ntddndis\ns-ntddndis-_ndis_routing_domain_isolation_entry.md">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a> structures in the array that follows the <a href="..\ntddndis\ns-ntddndis-_ndis_isolation_parameters.md">NDIS_ISOLATION_PARAMETERS</a> structure.

`RoutingDomainId`

The routing domain identifier for the VM network adapter. This identifier is  a GUID.

`RoutingDomainName`

An <a href="..\ntddndis\ns-ntddndis-_ndis_isolation_name.md">NDIS_ISOLATION_NAME</a> structure that contains the routing domain name for the VM network adapter.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.40 and later. Supported in NDIS 6.40 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn383690">OID_GEN_ISOLATION_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn383683">NDIS_ROUTING_DOMAIN_ENTRY_GET_NEXT</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_routing_domain_isolation_entry.md">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_isolation_parameters.md">NDIS_ISOLATION_PARAMETERS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_ROUTING_DOMAIN_ENTRY structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>