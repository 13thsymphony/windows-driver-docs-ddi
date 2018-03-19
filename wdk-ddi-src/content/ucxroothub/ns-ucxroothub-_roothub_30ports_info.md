---
UID: NS:ucxroothub._ROOTHUB_30PORTS_INFO
title: "_ROOTHUB_30PORTS_INFO"
author: windows-driver-content
description: Provides information about USB 3.0 root hub ports. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_30PORT_INFO callback function.
old-location: buses\_roothub_30ports_info.htm
old-project: usbref
ms.assetid: 2E727D84-193C-45AA-AEC4-75B72BB23FC9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PROOTHUB_30PORTS_INFO, P_ROOTHUB_30PORTS_INFO, P_ROOTHUB_30PORTS_INFO structure pointer [Buses], ROOTHUB_30PORTS_INFO, ROOTHUB_30PORTS_INFO structure [Buses], _ROOTHUB_30PORTS_INFO, buses._roothub_30ports_info, ucxroothub/P_ROOTHUB_30PORTS_INFO, ucxroothub/_ROOTHUB_30PORTS_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxroothub.h
api_name:
-	ROOTHUB_30PORTS_INFO
product: Windows
targetos: Windows
req.typenames: ROOTHUB_30PORTS_INFO, *PROOTHUB_30PORTS_INFO
req.product: Windows 10 or later.
---

# _ROOTHUB_30PORTS_INFO structure
Provides information about USB 3.0 root hub ports. This structure is passed by UCX in the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_get_30port_info.md">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a> callback function.

## Syntax
````
typedef struct _ROOTHUB_30PORTS_INFO {
  ULONG                 Size;
  USHORT                NumberOfPorts;
  USHORT                PortInfoSize;
   PROOTHUB_30PORT_INFO *PortInfoArray;
} ROOTHUB_30PORTS_INFO, *P_ROOTHUB_30PORTS_INFO;
````

## Members


`Size`

The size in bytes of this structure.

`NumberOfPorts`

Number of USB 3.0 root hub ports.

`PortInfoSize`

The size of the <a href="..\ucxroothub\ns-ucxroothub-_roothub_30port_info.md">ROOTHUB_30PORT_INFO</a> array.

`PortInfoArray`

A pointer to an array of  <a href="..\ucxroothub\ns-ucxroothub-_roothub_30port_info.md">ROOTHUB_30PORT_INFO</a> structures.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxroothub.h (include Ucxclass.h) |

## See Also

<a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_get_30port_info.md">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a>