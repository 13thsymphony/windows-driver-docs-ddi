---
UID: NS:ndis._NDIS_IF_PROVIDER_CHARACTERISTICS
title: "_NDIS_IF_PROVIDER_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_IF_PROVIDER_CHARACTERISTICS structure defines NDIS network interface provider entry points and other provider characteristics.
old-location: netvista\ndis_if_provider_characteristics.htm
old-project: netvista
ms.assetid: f295bea2-20d8-4c71-b78b-77d43840be2a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PNDIS_IF_PROVIDER_CHARACTERISTICS, _NDIS_IF_PROVIDER_CHARACTERISTICS, ndis/NDIS_IF_PROVIDER_CHARACTERISTICS, PNDIS_IF_PROVIDER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], ndis/PNDIS_IF_PROVIDER_CHARACTERISTICS, netvista.ndis_if_provider_characteristics, NDIS_IF_PROVIDER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_IF_PROVIDER_CHARACTERISTICS, NDIS_IF_PROVIDER_CHARACTERISTICS, net_if_struct_ref_44fd781f-d830-4a18-86e9-b16eb3367d6a.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NDIS_IF_PROVIDER_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: "*PNDIS_IF_PROVIDER_CHARACTERISTICS, NDIS_IF_PROVIDER_CHARACTERISTICS"
---

# _NDIS_IF_PROVIDER_CHARACTERISTICS structure
The NDIS_IF_PROVIDER_CHARACTERISTICS structure defines NDIS network interface provider entry points
  and other provider characteristics.

## Syntax
````
typedef struct _NDIS_IF_PROVIDER_CHARACTERISTICS {
  NDIS_OBJECT_HEADER Header;
  IFP_QUERY_OBJECT   QueryObjectHandler;
  IFP_SET_OBJECT     SetObjectHandler;
  PVOID              Reserved1;
  PVOID              Reserved2;
} NDIS_IF_PROVIDER_CHARACTERISTICS, *PNDIS_IF_PROVIDER_CHARACTERISTICS;
````

## Members


`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     interface provider characteristics structure (NDIS_IF_PROVIDER_CHARACTERISTICS). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_OBJECT_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_IF_PROVIDER_CHARACTERISTICS_REVISION_1.

`QueryObjectHandler`

The entry point for the 
     <a href="..\ndis\nc-ndis-if_query_object.md">
     ProviderQueryObject</a> function.

`Reserved1`

Reserved for NDIS.

`Reserved2`

Reserved for NDIS.

`SetObjectHandler`

The entry point for the 
     <a href="..\ndis\nc-ndis-if_set_object.md">ProviderSetObject</a> function.

## Remarks
All NDIS network driver types can register as network interface providers. An NDIS interface provider
    initializes an NDIS_IF_PROVIDER_CHARACTERISTICS structure to define its provider entry points and other
    characteristics, if any.

To register as an interface provider, the driver passes a pointer to the initialized
    NDIS_IF_PROVIDER_CHARACTERISTICS structure to the 
    <a href="..\ndis\nf-ndis-ndisifregisterprovider.md">
    NdisIfRegisterProvider</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\ndis\nc-ndis-if_query_object.md">ProviderQueryObject</a>

<a href="..\ndis\nf-ndis-ndisifregisterprovider.md">NdisIfRegisterProvider</a>

<a href="..\ndis\nc-ndis-if_set_object.md">ProviderSetObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_IF_PROVIDER_CHARACTERISTICS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>