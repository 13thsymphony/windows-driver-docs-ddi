---
UID: NS.NDIS._NDIS_IF_PROVIDER_CHARACTERISTICS
title: _NDIS_IF_PROVIDER_CHARACTERISTICS
author: windows-driver-content
description: The NDIS_IF_PROVIDER_CHARACTERISTICS structure defines NDIS network interface provider entry points and other provider characteristics.
old-location: netvista\ndis_if_provider_characteristics.htm
old-project: netvista
ms.assetid: f295bea2-20d8-4c71-b78b-77d43840be2a
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_IF_PROVIDER_CHARACTERISTICS, *PNDIS_IF_PROVIDER_CHARACTERISTICS, NDIS_IF_PROVIDER_CHARACTERISTICS
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
req.alt-api: NDIS_IF_PROVIDER_CHARACTERISTICS
req.alt-loc: ndis.h
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
---

# _NDIS_IF_PROVIDER_CHARACTERISTICS structure



## -description
The NDIS_IF_PROVIDER_CHARACTERISTICS structure defines NDIS network interface provider entry points
  and other provider characteristics.



## -syntax

````
typedef struct _NDIS_IF_PROVIDER_CHARACTERISTICS {
  NDIS_OBJECT_HEADER Header;
  IFP_QUERY_OBJECT   QueryObjectHandler;
  IFP_SET_OBJECT     SetObjectHandler;
  PVOID              Reserved1;
  PVOID              Reserved2;
} NDIS_IF_PROVIDER_CHARACTERISTICS, *PNDIS_IF_PROVIDER_CHARACTERISTICS;
````


## -struct-fields

### -field Header

The 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     interface provider characteristics structure (NDIS_IF_PROVIDER_CHARACTERISTICS). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_OBJECT_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_IF_PROVIDER_CHARACTERISTICS_REVISION_1.


### -field QueryObjectHandler

The entry point for the 
     <a href="..\ndis\nc-ndis-if_query_object.md">
     ProviderQueryObject</a> function.


### -field SetObjectHandler

The entry point for the 
     <a href="..\ndis\nc-ndis-if_set_object.md">ProviderSetObject</a> function.


### -field Reserved1

Reserved for NDIS.


### -field Reserved2

Reserved for NDIS.


## -remarks
All NDIS network driver types can register as network interface providers. An NDIS interface provider
    initializes an NDIS_IF_PROVIDER_CHARACTERISTICS structure to define its provider entry points and other
    characteristics, if any.

To register as an interface provider, the driver passes a pointer to the initialized
    NDIS_IF_PROVIDER_CHARACTERISTICS structure to the 
    <a href="netvista.ndisifregisterprovider">
    NdisIfRegisterProvider</a> function.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndisifregisterprovider">NdisIfRegisterProvider</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-if_query_object.md">ProviderQueryObject</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-if_set_object.md">ProviderSetObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_IF_PROVIDER_CHARACTERISTICS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

