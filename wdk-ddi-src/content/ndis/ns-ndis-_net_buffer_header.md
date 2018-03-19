---
UID: NS:ndis._NET_BUFFER_HEADER
title: "_NET_BUFFER_HEADER"
author: windows-driver-content
description: The NET_BUFFER_HEADER structure specifies header information for the NET_BUFFER structure.
old-location: netvista\net_buffer_header.htm
old-project: netvista
ms.assetid: db7277d0-9671-4680-84d4-d3415ce3922f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNET_BUFFER_HEADER, NET_BUFFER_HEADER, NET_BUFFER_HEADER union [Network Drivers Starting with Windows Vista], PNET_BUFFER_HEADER, PNET_BUFFER_HEADER union pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER_HEADER, ndis/NET_BUFFER_HEADER, ndis/PNET_BUFFER_HEADER, ndis_netbuf_structures_ref_a19368c6-0bef-4fe6-be52-d76e0c6ea99d.xml, netvista.net_buffer_header"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NET_BUFFER_HEADER
product: Windows
targetos: Windows
req.typenames: NET_BUFFER_HEADER, *PNET_BUFFER_HEADER
---

# _NET_BUFFER_HEADER structure
The NET_BUFFER_HEADER structure specifies header information for the 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure.

## Syntax
````
typedef union _NET_BUFFER_HEADER {
  NET_BUFFER_DATA NetBufferData;
  SLIST_HEADER    Link;
} NET_BUFFER_HEADER, *PNET_BUFFER_HEADER;
````

## Members


`NetBufferData`

A 
     <a href="..\ndis\ns-ndis-_net_buffer_data.md">NET_BUFFER_DATA</a> structure.

`Link`

Reserved for NDIS.

## Remarks
NDIS maintains the information in the NET_BUFFER_HEADER union.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\ns-ndis-_net_buffer_data.md">NET_BUFFER_DATA</a>