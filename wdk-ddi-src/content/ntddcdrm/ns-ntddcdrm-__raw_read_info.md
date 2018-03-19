---
UID: NS:ntddcdrm.__RAW_READ_INFO
title: "__RAW_READ_INFO"
author: windows-driver-content
description: The RAW_READ_INFO structure is used in conjunction with the IOCTL_CDROM_RAW_READ request to read data from a CD-ROM in raw mode.
old-location: storage\raw_read_info.htm
old-project: storage
ms.assetid: 8786545d-39b2-4331-9d62-3b345eb58d1f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PRAW_READ_INFO, PRAW_READ_INFO, PRAW_READ_INFO structure pointer [Storage Devices], RAW_READ_INFO, RAW_READ_INFO structure [Storage Devices], __RAW_READ_INFO, ntddcdrm/PRAW_READ_INFO, ntddcdrm/RAW_READ_INFO, storage.raw_read_info, structs-CD-ROM_4414d6ab-7048-4977-b373-58d1240f5262.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	ntddcdrm.h
api_name:
-	RAW_READ_INFO
product: Windows
targetos: Windows
req.typenames: RAW_READ_INFO, *PRAW_READ_INFO
---

# __RAW_READ_INFO structure
The RAW_READ_INFO structure is used in conjunction with the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_raw_read.md">IOCTL_CDROM_RAW_READ</a> request to read data from a CD-ROM in raw mode.

## Syntax
````
typedef struct __RAW_READ_INFO {
  LARGE_INTEGER   DiskOffset;
  ULONG           SectorCount;
  TRACK_MODE_TYPE TrackMode;
} RAW_READ_INFO, *PRAW_READ_INFO;
````

## Members


`DiskOffset`

Contains an offset into the CD-ROM disc where data will be read. You can  calculate this offset by multiplying the starting sector number for the request times 2048.

`SectorCount`

Contains the number of sectors to read.

`TrackMode`

Contains an enumerator of type <a href="..\ntddcdrm\ne-ntddcdrm-_track_mode_type.md">TRACK_MODE_TYPE</a> that indicates the type of the track mode.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddcdrm\ne-ntddcdrm-_track_mode_type.md">TRACK_MODE_TYPE</a>



<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_raw_read.md">IOCTL_CDROM_RAW_READ</a>