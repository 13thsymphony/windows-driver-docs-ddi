---
UID: NS:ntdddisk._DISK_INT13_INFO
title: "_DISK_INT13_INFO"
author: windows-driver-content
description: The DISK_INT13_INFO structure is used by the BIOS to report disk detection data for a partition with an INT13 format.
old-location: storage\disk_int13_info.htm
old-project: storage
ms.assetid: 8a9c335a-1c5f-4379-83bb-21391ae46a3c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDISK_INT13_INFO, DISK_INT13_INFO, DISK_INT13_INFO structure [Storage Devices], PDISK_INT13_INFO, PDISK_INT13_INFO structure pointer [Storage Devices], _DISK_INT13_INFO, ntdddisk/DISK_INT13_INFO, ntdddisk/PDISK_INT13_INFO, storage.disk_int13_info, structs-disk_fc6ee399-d876-44e3-955a-3ab95c1b5134.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	ntdddisk.h
api_name:
-	DISK_INT13_INFO
product: Windows
targetos: Windows
req.typenames: DISK_INT13_INFO, *PDISK_INT13_INFO
---

# _DISK_INT13_INFO structure
The DISK_INT13_INFO structure is used by the BIOS to report disk detection data for a partition with an INT13 format.

## Syntax
````
typedef struct _DISK_INT13_INFO {
  USHORT DriveSelect;
  ULONG  MaxCylinders;
  USHORT SectorsPerTrack;
  USHORT MaxHeads;
  USHORT NumberDrives;
} DISK_INT13_INFO, *PDISK_INT13_INFO;
````

## Members


`DriveSelect`

Corresponds to the Device/Head register defined in the <i>AT Attachment (ATA)</i> specification. When zero, the fourth bit of this register indicates that drive zero is selected. When 1, it indicates that drive one is selected. The values of bits 0, 1, 2, 3, and 6 depend on the command in the command register. Bits 5 and 7 are no longer used. For more information about the values that the Device/Head register can hold, see the ATA specification.

`MaxCylinders`

Indicates the maximum number of cylinders on the disk.

`SectorsPerTrack`

Indicates the number of sectors per track.

`MaxHeads`

Indicates the maximum number of disk heads.

`NumberDrives`

Indicates the number of drives.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="..\ntdddisk\ns-ntdddisk-_disk_ex_int13_info.md">DISK_EX_INT13_INFO</a>



<a href="..\ntdddisk\ns-ntdddisk-_disk_detection_info.md">DISK_DETECTION_INFO</a>