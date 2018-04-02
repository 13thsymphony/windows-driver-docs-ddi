---
UID: NS:1394._TOPOLOGY_MAP
title: "_TOPOLOGY_MAP"
author: windows-driver-content
description: The TOPOLOGY_MAP structure is used to store an IEEE 1394 bus topology map. The relations between devices are found in the port members of the entries in TOP_Self_ID_Array.
old-location: ieee\topology_map.htm
old-project: IEEE
ms.assetid: 0a4c7ffc-94f9-4068-b650-1da43e45d0ad
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PTOPOLOGY_MAP, 1394/PTOPOLOGY_MAP, 1394/TOPOLOGY_MAP, 1394stct_4afaf64f-e60c-4521-91c7-82abefd49b55.xml, IEEE.topology_map, PTOPOLOGY_MAP, PTOPOLOGY_MAP structure pointer [Buses], TOPOLOGY_MAP, TOPOLOGY_MAP structure [Buses], _TOPOLOGY_MAP"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1394.h
api_name:
-	TOPOLOGY_MAP
product: Windows
targetos: Windows
req.typenames: TOPOLOGY_MAP, *PTOPOLOGY_MAP
---

# _TOPOLOGY_MAP structure
The TOPOLOGY_MAP structure is used to store an IEEE 1394 bus topology map. The relations between devices are found in the port members of the entries in <b>TOP_Self_ID_Array</b>.

## Syntax
```
typedef struct _TOPOLOGY_MAP {
  USHORT  TOP_Length;
  USHORT  TOP_CRC;
  ULONG   TOP_Generation;
  USHORT  TOP_Node_Count;
  USHORT  TOP_Self_ID_Count;
  SELF_ID TOP_Self_ID_Array[1];
} TOPOLOGY_MAP, *PTOPOLOGY_MAP;
```

## Members


`TOP_Length`

Specifies the length in quadlets of the topology map.

`TOP_CRC`

Specifies the CRC value for the topology map.

`TOP_Generation`

Specifies the bus reset generation for which the topology map was created.

`TOP_Node_Count`

Specifies the number of nodes in the topology map.

`TOP_Self_ID_Count`

Specifies the number of entries in <b>TOP_Self_ID_Array</b>.

`TOP_Self_ID_Array`

Pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff538073">SELF_ID</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff538080">SELF_ID_MORE</a> structures (the two structures are the same size).

## Remarks
All data will be in big-endian format.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 1394.h (include 1394.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537646">REQUEST_GET_SPEED_TOPOLOGY_MAPS</a>