---
UID: NE.ntddndis._NDIS_ARP_HEADER_FIELD
title: _NDIS_ARP_HEADER_FIELD
author: windows-driver-content
description: The NDIS_ARP_HEADER_FIELD enumeration identifies the type of a field in an Address Resolution Protocol (ARP) header.
old-location: netvista\ndis_arp_header_field.htm
old-project: netvista
ms.assetid: 63DA6329-C673-48A0-8E36-67035E2DB4C9
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_ARP_HEADER_FIELD, NDIS_ARP_HEADER_FIELD, *PNDIS_ARP_HEADER_FIELD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_ARP_HEADER_FIELD
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

# _NDIS_ARP_HEADER_FIELD enumeration



## -description
The <b>NDIS_ARP_HEADER_FIELD</b> enumeration identifies the type of a field in an Address Resolution Protocol (ARP) header.



## -syntax

````
typedef enum _NDIS_ARP_HEADER_FIELD { 
  NdisARPHeaderFieldUndefined,
  NdisARPHeaderFieldOperation,
  NdisARPHeaderFieldSPA,
  NdisARPHeaderFieldTPA,
  NdisARPHeaderFieldMaximum
} NDIS_ARP_HEADER_FIELD, *PNDIS_ARP_HEADER_FIELD;
````


## -enum-fields

### -field NdisARPHeaderFieldUndefined

An undefined ARP header field.


### -field NdisARPHeaderFieldOperation

The ARP operation field.


### -field NdisARPHeaderFieldSPA

The ARP source protocol address (SPA) field.


### -field NdisARPHeaderFieldTPA

The ARP target protocol address (TPA) field.


### -field NdisARPHeaderFieldMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks
The <b>NDIS_ARP_HEADER_FIELD</b> enumeration is used in the 
    <a href="netvista.ndis_receive_filter_field_parameters">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.30 and later.

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
<a href="netvista.ndis_receive_filter_field_parameters">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_ARP_HEADER_FIELD enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

