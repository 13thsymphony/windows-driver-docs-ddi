---
UID: NS:ntdddisk._PARTITION_INFORMATION_MBR
title: "_PARTITION_INFORMATION_MBR"
author: windows-driver-content
description: PARTITION_INFORMATION_MBR contains information for a Master Boot Record partition that is not held in common with a GUID Partition Table partition.
old-location: storage\partition_information_mbr.htm
old-project: storage
ms.assetid: 846f3a1c-ee0a-42d2-bdf1-7bf09406c955
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PPARTITION_INFORMATION_MBR, PARTITION_INFORMATION_MBR, PARTITION_INFORMATION_MBR structure [Storage Devices], PPARTITION_INFORMATION_MBR, PPARTITION_INFORMATION_MBR structure pointer [Storage Devices], _PARTITION_INFORMATION_MBR, ntdddisk/PARTITION_INFORMATION_MBR, ntdddisk/PPARTITION_INFORMATION_MBR, storage.partition_information_mbr, structs-disk_c386ea16-c8d7-4a5e-8e61-d8e8ddead136.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntddk.h, Ntdddisk.h
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
-	PARTITION_INFORMATION_MBR
product: Windows
targetos: Windows
req.typenames: PARTITION_INFORMATION_MBR, *PPARTITION_INFORMATION_MBR
---

# _PARTITION_INFORMATION_MBR structure
PARTITION_INFORMATION_MBR contains information for a Master Boot Record partition that is not held in common with a GUID Partition Table partition.

## Syntax
```
typedef struct _PARTITION_INFORMATION_MBR {
  __WRAPPED__ UCHAR   PartitionType;
  __WRAPPED__ BOOLEAN BootIndicator;
  __WRAPPED__ BOOLEAN RecognizedPartition;
  __WRAPPED__ ULONG   HiddenSectors;
  __WRAPPED__ GUID    PartitionId;
} PARTITION_INFORMATION_MBR, *PPARTITION_INFORMATION_MBR;
```

## Members


`PartitionType`

Specifies the partition type. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff563751">PARTITION_INFORMATION</a> for a list of system-defined partition types.

`BootIndicator`

Indicates, when <b>TRUE</b>, that the partition is bootable. When <b>FALSE</b>, the partition is not bootable.

`RecognizedPartition`

Indicates, when <b>TRUE</b>, that this is a partition with a recognized partition type. When <b>FALSE</b> this is a not a partition with a recognized partition.

`HiddenSectors`

Contains the number of hidden sectors in the partition.

`PartitionId`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntddk.h, Ntdddisk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561452">IoReadPartitionTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563754">PARTITION_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563763">PARTITION_INFORMATION_GPT</a>