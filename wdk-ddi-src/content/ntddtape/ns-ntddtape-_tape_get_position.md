---
UID: NS:ntddtape._TAPE_GET_POSITION
title: "_TAPE_GET_POSITION"
author: windows-driver-content
description: The TAPE_GET_POSITION structure is used in conjunction with the IOCTL_TAPE_GET_POSITION request to retrieve the current absolute, logical, or pseudological partition and offset position on the tape.
old-location: storage\tape_get_position.htm
old-project: storage
ms.assetid: dd7a194a-6ce4-4889-b574-7c4f232f45f0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PTAPE_GET_POSITION, PTAPE_GET_POSITION, PTAPE_GET_POSITION structure pointer [Storage Devices], TAPE_GET_POSITION, TAPE_GET_POSITION structure [Storage Devices], _TAPE_GET_POSITION, ntddtape/PTAPE_GET_POSITION, ntddtape/TAPE_GET_POSITION, storage.tape_get_position, structs-tape_e80e5f0f-02d5-4745-a2d1-3d94e8dc9959.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddtape.h
req.include-header: Ntddtape.h, Minitape.h
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
-	ntddtape.h
api_name:
-	TAPE_GET_POSITION
product: Windows
targetos: Windows
req.typenames: TAPE_GET_POSITION, *PTAPE_GET_POSITION
---

# _TAPE_GET_POSITION structure
The TAPE_GET_POSITION structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560622">IOCTL_TAPE_GET_POSITION</a> request to retrieve the current absolute, logical, or pseudological partition and offset position on the tape.

## Syntax
```
typedef struct _TAPE_GET_POSITION {
  ULONG         Type;
  ULONG         Partition;
  LARGE_INTEGER Offset;
} *PTAPE_GET_POSITION, TAPE_GET_POSITION;
```

## Members


`Type`

Indicates the type of position requested. This member can be TAPE_ABSOLUTE_POSITION, TAPE_LOGICAL_POSITION, or TAPE_PSEUDO_LOGICAL_POSITION.

`Partition`

Indicates the number of the partition where the current position is located.

`Offset`

Indicates the number of bytes from the beginning of the partition to the current position.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddtape.h (include Ntddtape.h, Minitape.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560622">IOCTL_TAPE_GET_POSITION</a>