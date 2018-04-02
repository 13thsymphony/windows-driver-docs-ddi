---
UID: NS:ntddndis._NDIS_PORT
title: "_NDIS_PORT"
author: windows-driver-content
description: The NDIS_PORT structure specifies the characteristics of an NDIS port and a pointer to the next element in a linked list of ports.
old-location: netvista\ndis_port.htm
old-project: netvista
ms.assetid: aef1b7b2-73d3-49ad-a3f2-c06fa1f34839
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_PORT, NDIS_PORT, NDIS_PORT structure [Network Drivers Starting with Windows Vista], PNDIS_PORT, PNDIS_PORT structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PORT, ndis_ports_ref_df9a02e1-4a6b-4901-8794-37a5e30ececb.xml, netvista.ndis_port, ntddndis/NDIS_PORT, ntddndis/PNDIS_PORT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	NDIS_PORT
product: Windows
targetos: Windows
req.typenames: NDIS_PORT, *PNDIS_PORT
---

# _NDIS_PORT structure
The NDIS_PORT structure specifies the characteristics of an NDIS port and a pointer to the next
  element in a linked list of ports.

## Syntax
```
typedef struct _NDIS_PORT {
  PNDIS_PORT                Next;
  PVOID                     NdisReserved;
  PVOID                     MiniportReserved;
  PVOID                     ProtocolReserved;
  NDIS_PORT_CHARACTERISTICS PortCharacteristics;
} NDIS_PORT, *PNDIS_PORT;
```

## Members


`Next`

A pointer to the next port in the linked list of ports.

`NdisReserved`

Reserved for NDIS.

`MiniportReserved`

Reserved for miniport drivers.

`ProtocolReserved`

Reserved for protocol drivers.

`PortCharacteristics`

An 
     <a href="https://msdn.microsoft.com/fd602dd6-c216-413a-a4da-292739774937">
     NDIS_PORT_CHARACTERISTICS</a> structure that specifies the characteristics of the port.

## Remarks
The NDIS_PORT structure is used to create a linked list of ports. Such a linked list is used in port
    activation (<b>NetEventPortActivation</b>) Plug and Play (PnP) events.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566791">NDIS_PORT_CHARACTERISTICS</a>