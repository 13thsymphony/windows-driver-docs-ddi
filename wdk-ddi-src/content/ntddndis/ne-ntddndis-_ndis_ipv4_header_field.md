---
UID : NE:ntddndis._NDIS_IPV4_HEADER_FIELD
title : "_NDIS_IPV4_HEADER_FIELD"
author : windows-driver-content
description : The NDIS_IPV4_HEADER_FIELD enumeration identifies the type of a field in an IP version 4 (IPv4) header to be filtered.
old-location : netvista\ndis_ipv4_header_field.htm
old-project : netvista
ms.assetid : 5B7C4107-1724-473C-8F36-C345A056F3DC
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NDIS_IPV4_HEADER_FIELD enumeration [Network Drivers Starting with Windows Vista], netvista.ndis_ipv4_header_field, ntddndis/NDIS_IPV4_HEADER_FIELD, ntddndis/NdisIPv4HeaderFieldUndefined, NdisIPv4HeaderFieldUndefined, *PNDIS_IPV4_HEADER_FIELD, _NDIS_IPV4_HEADER_FIELD, NdisIPv4HeaderFieldProtocol, PNDIS_IPV4_HEADER_FIELD, NdisIPv4HeaderFieldMaximum, NDIS_IPV4_HEADER_FIELD, PNDIS_IPV4_HEADER_FIELD enumeration pointer [Network Drivers Starting with Windows Vista], ntddndis/PNDIS_IPV4_HEADER_FIELD, ntddndis/NdisIPv4HeaderFieldMaximum, ntddndis/NdisIPv4HeaderFieldProtocol
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.30 and later.
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
req.typenames : NDIS_IPV4_HEADER_FIELD, *PNDIS_IPV4_HEADER_FIELD
---

# _NDIS_IPV4_HEADER_FIELD Enumeration
The <b>NDIS_IPV4_HEADER_FIELD</b> enumeration identifies the type of a field in an IP version 4 (IPv4) header to be filtered.

## Syntax
````
typedef enum _NDIS_IPV4_HEADER_FIELD { 
  NdisIPv4HeaderFieldUndefined,
  NdisIPv4HeaderFieldProtocol,
  NdisIPv4HeaderFieldMaximum
} NDIS_IPV4_HEADER_FIELD, *PNDIS_IPV4_HEADER_FIELD;
````

## Constants

<table>

<tr>
<td>NdisIPv4HeaderFieldMaximum</td>
<td>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</td>
</tr>

<tr>
<td>NdisIPv4HeaderFieldProtocol</td>
<td>The IPv4 protocol field.</td>
</tr>

<tr>
<td>NdisIPv4HeaderFieldUndefined</td>
<td>An undefined IPV4 header field.</td>
</tr>
</table>

## Remarks

The <b>NDIS_IPV4_HEADER_FIELD</b> enumeration is used in the 
    <a href="..\ntddndis\ns-ntddndis-_ndis_receive_filter_field_parameters.md">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_receive_filter_field_parameters.md">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_IPV4_HEADER_FIELD enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>