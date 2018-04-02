---
UID: NS:ntddcdvd.DVD_READ_STRUCTURE
title: DVD_READ_STRUCTURE
author: windows-driver-content
description: The DVD_READ_STRUCTURE structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD descriptor containing information about a DVD disc.
old-location: storage\dvd_read_structure.htm
old-project: storage
ms.assetid: fe8c55de-e542-4c0d-a96b-31ad39e11dff
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDVD_READ_STRUCTURE, DVD_READ_STRUCTURE, DVD_READ_STRUCTURE structure [Storage Devices], PDVD_READ_STRUCTURE, PDVD_READ_STRUCTURE structure pointer [Storage Devices], ntddcdvd/DVD_READ_STRUCTURE, ntddcdvd/PDVD_READ_STRUCTURE, storage.dvd_read_structure, structs-DVD_64ffaf42-815a-4a1e-a712-7027930d099f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
-	ntddcdvd.h
api_name:
-	DVD_READ_STRUCTURE
product:
- Windows
targetos: Windows
req.typenames: DVD_READ_STRUCTURE, *PDVD_READ_STRUCTURE
---

# DVD_READ_STRUCTURE structure
The DVD_READ_STRUCTURE structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560426">IOCTL_DVD_READ_STRUCTURE</a> request to retrieve a DVD descriptor containing information about a DVD disc.

## Syntax
```
typedef struct DVD_READ_STRUCTURE {
  LARGE_INTEGER        BlockByteOffset;
  DVD_STRUCTURE_FORMAT Format;
  DVD_SESSION_ID       SessionId;
  UCHAR                LayerNumber;
}  *PDVD_READ_STRUCTURE;
```

## Members


`BlockByteOffset`

Contains an offset to the logical block address of the descriptor to be retrieved.

`Format`

Indicates the type of DVD descriptor to retrieve. See the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553750">DVD_STRUCTURE_FORMAT</a> enumeration type for further information about the values that can be assigned to this member.

`SessionId`

Contains the DVD session ID.

`LayerNumber`

Contains the number of the layer where the descriptor is to be retrieved.

## Remarks
The DVD_READ_STRUCTURE structure contains data such as copyright information, or manufacturer-specific information.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdvd.h (include Ntddcdvd.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553750">DVD_STRUCTURE_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560426">IOCTL_DVD_READ_STRUCTURE</a>