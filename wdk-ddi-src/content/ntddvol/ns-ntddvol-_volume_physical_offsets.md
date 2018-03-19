---
UID: NS:ntddvol._VOLUME_PHYSICAL_OFFSETS
title: "_VOLUME_PHYSICAL_OFFSETS"
author: windows-driver-content
description: The VOLUME_PHYSICAL_OFFSETS structure contains an array of physical offsets and accompanying physical disk numbers and is used with IOCTL_VOLUME_LOGICAL_TO_PHYSICAL to request a series of pairs of physical offsets and disk numbers that correspond to a single logical offset.
old-location: storage\volume_physical_offsets.htm
old-project: storage
ms.assetid: 876cb283-ce0d-44ed-b515-d4ee31089b88
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PVOLUME_PHYSICAL_OFFSETS, PVOLUME_PHYSICAL_OFFSETS, PVOLUME_PHYSICAL_OFFSETS structure pointer [Storage Devices], VOLUME_PHYSICAL_OFFSETS, VOLUME_PHYSICAL_OFFSETS structure [Storage Devices], _VOLUME_PHYSICAL_OFFSETS, ntddvol/PVOLUME_PHYSICAL_OFFSETS, ntddvol/VOLUME_PHYSICAL_OFFSETS, storage.volume_physical_offsets, structs-volumemgr_f5ee82b1-a42a-47aa-a3fd-116eeb3b441b.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvol.h
req.include-header: Ntddvol.h
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
-	ntddvol.h
api_name:
-	VOLUME_PHYSICAL_OFFSETS
product: Windows
targetos: Windows
req.typenames: VOLUME_PHYSICAL_OFFSETS, *PVOLUME_PHYSICAL_OFFSETS
---

# _VOLUME_PHYSICAL_OFFSETS structure
The VOLUME_PHYSICAL_OFFSETS structure contains an array of physical offsets and accompanying physical disk numbers and is used with <a href="..\ntddvol\ni-ntddvol-ioctl_volume_logical_to_physical.md">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a> to request a series of pairs of physical offsets and disk numbers that correspond to a single logical offset.

## Syntax
````
typedef struct _VOLUME_PHYSICAL_OFFSETS {
  ULONG                  NumberOfPhysicalOffsets;
  VOLUME_PHYSICAL_OFFSET PhysicalOffset[ANYSIZE_ARRAY];
} VOLUME_PHYSICAL_OFFSETS, *PVOLUME_PHYSICAL_OFFSETS;
````

## Members


`NumberOfPhysicalOffsets`

Contains the number of physical offsets returned by the call to <a href="..\ntddvol\ni-ntddvol-ioctl_volume_logical_to_physical.md">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a>.

`PhysicalOffset`

Contains an array of structures of type <a href="..\ntddvol\ns-ntddvol-_volume_physical_offset.md">VOLUME_PHYSICAL_OFFSET</a>. Each element of the array contains a pair consisting of a physical disk number and an accompanying physical offset &lt;disk number, disk offset&gt;.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddvol.h (include Ntddvol.h) |

## See Also

<a href="..\ntddvol\ns-ntddvol-_volume_physical_offset.md">VOLUME_PHYSICAL_OFFSET</a>



<a href="..\ntddvol\ni-ntddvol-ioctl_volume_logical_to_physical.md">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a>



<a href="..\ntddvol\ni-ntddvol-ioctl_volume_physical_to_logical.md">IOCTL_VOLUME_PHYSICAL_TO_LOGICAL</a>