---
UID: NS:ntdddisk._DISK_GEOMETRY
title: "_DISK_GEOMETRY"
author: windows-driver-content
description: The DISK_GEOMETRY structure is obsolete and provided only to support existing drivers.
old-location: storage\disk_geometry.htm
old-project: storage
ms.assetid: f92d1f63-4361-4775-88f8-be1c9bf781ef
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDISK_GEOMETRY, DISK_GEOMETRY, DISK_GEOMETRY structure [Storage Devices], PDISK_GEOMETRY, PDISK_GEOMETRY structure pointer [Storage Devices], _DISK_GEOMETRY, ntdddisk/DISK_GEOMETRY, ntdddisk/PDISK_GEOMETRY, storage.disk_geometry, structs-disk_3ad908b7-8f42-4a06-914e-92b631cc1a56.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h, Ntddk.h, Ntdddisk.h
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
-	DISK_GEOMETRY
product: Windows
targetos: Windows
req.typenames: DISK_GEOMETRY, *PDISK_GEOMETRY
---

# _DISK_GEOMETRY structure
The DISK_GEOMETRY structure is obsolete and provided only to support existing drivers. New drivers must use <a href="https://msdn.microsoft.com/library/windows/hardware/ff552618">DISK_GEOMETRY_EX</a>. DISK_GEOMETRY is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560357">IOCTL_DISK_GET_DRIVE_GEOMETRY</a> and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560371">IOCTL_DISK_GET_MEDIA_TYPES</a> requests, in order to retrieve information about the geometry of a physical disk.

## Syntax
```
typedef struct _DISK_GEOMETRY {
  __WRAPPED__ LARGE_INTEGER Cylinders;
  __WRAPPED__ MEDIA_TYPE    MediaType;
  __WRAPPED__ ULONG         TracksPerCylinder;
  __WRAPPED__ ULONG         SectorsPerTrack;
  __WRAPPED__ ULONG         BytesPerSector;
} *PDISK_GEOMETRY, DISK_GEOMETRY;
```

## Members


`Cylinders`

Indicates the number of cylinders on the disk device.

`MediaType`

Indicates the type of disk. The enumeration <a href="https://msdn.microsoft.com/library/windows/hardware/ff562216">MEDIA_TYPE</a> lists the values that can be assigned to this member.

`TracksPerCylinder`

Indicates the number of tracks in a cylinder.

`SectorsPerTrack`

Indicates the number of sectors in each track.

`BytesPerSector`

Indicates the number of bytes in a disk sector.

## Remarks
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552618">DISK_GEOMETRY_EX</a> must be used with new drivers, in order to accommodate GUID Partition Table (GPT) partitions. The DISK_GEOMETRY structure is nested within the DISK_GEOMETRY_EX structure.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff560371">IOCTL_DISK_GET_MEDIA_TYPES</a> causes an array of these structures to be returned.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h, Ntddk.h, Ntdddisk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552618">DISK_GEOMETRY_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560357">IOCTL_DISK_GET_DRIVE_GEOMETRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560371">IOCTL_DISK_GET_MEDIA_TYPES</a>