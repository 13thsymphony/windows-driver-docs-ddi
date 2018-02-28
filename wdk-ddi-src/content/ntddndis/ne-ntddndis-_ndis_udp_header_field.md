---
UID: NE:ntddndis._NDIS_UDP_HEADER_FIELD
title: "_NDIS_UDP_HEADER_FIELD"
author: windows-driver-content
description: The NDIS_UDP_HEADER_FIELD enumeration identifies the type of a field in a User Datagram Protocol (UDP) header to be filtered.
old-location: netvista\ndis_udp_header_field.htm
old-project: netvista
ms.assetid: 8AB1661D-A7DF-4178-8D1A-87A3AF9C4316
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_UDP_HEADER_FIELD, NDIS_UDP_HEADER_FIELD, NDIS_UDP_HEADER_FIELD enumeration [Network Drivers Starting with Windows Vista], NdisUdpHeaderFieldDestinationPort, NdisUdpHeaderFieldMaximum, NdisUdpHeaderFieldUndefined, PNDIS_UDP_HEADER_FIELD, PNDIS_UDP_HEADER_FIELD enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_UDP_HEADER_FIELD, netvista.ndis_udp_header_field, ntddndis/NDIS_UDP_HEADER_FIELD, ntddndis/NdisUdpHeaderFieldDestinationPort, ntddndis/NdisUdpHeaderFieldMaximum, ntddndis/NdisUdpHeaderFieldUndefined, ntddndis/PNDIS_UDP_HEADER_FIELD"
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
-	NDIS_UDP_HEADER_FIELD
product: Windows
targetos: Windows
req.typenames: NDIS_UDP_HEADER_FIELD, *PNDIS_UDP_HEADER_FIELD
---

# _NDIS_UDP_HEADER_FIELD Enumeration
The <b>NDIS_UDP_HEADER_FIELD</b> enumeration identifies the type of a field in a User Datagram Protocol
(UDP) header to be filtered.

## Syntax
````
typedef enum _NDIS_UDP_HEADER_FIELD { 
  NdisUdpHeaderFieldUndefined,
  NdisUdpHeaderFieldDestinationPort,
  NdisUdpHeaderFieldMaximum
} NDIS_UDP_HEADER_FIELD, *PNDIS_UDP_HEADER_FIELD;
````

## Constants

<table>
            
                <tr>
                    <td>NdisUdpHeaderFieldDestinationPort</td>
                    <td>The UDP destination port field.</td>
                </tr>
            
                <tr>
                    <td>NdisUdpHeaderFieldMaximum</td>
                    <td>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</td>
                </tr>
            
                <tr>
                    <td>NdisUdpHeaderFieldUndefined</td>
                    <td>An undefined UDP header field.</td>
                </tr>
</table>

## Remarks

The <b>NDIS_UDP_HEADER_FIELD</b> enumeration is used in the 
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_UDP_HEADER_FIELD enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>