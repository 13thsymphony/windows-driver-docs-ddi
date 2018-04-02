---
UID: NS:ntdddisk._CREATE_DISK
title: "_CREATE_DISK"
author: windows-driver-content
description: The CREATE_DISK structure is used with the IOCTL_DISK_CREATE_DISK IOCTL to initialize a disk with an empty partition table. The partition table styles are master boot record (MBR) or GUID partition table (GPT).
old-location: storage\create_disk.htm
old-project: storage
ms.assetid: 20989831-5ff0-4457-9dae-ceaf34830a2e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PCREATE_DISK, CREATE_DISK, CREATE_DISK structure [Storage Devices], PCREATE_DISK, PCREATE_DISK structure pointer [Storage Devices], _CREATE_DISK, ntdddisk/CREATE_DISK, ntdddisk/PCREATE_DISK, storage.create_disk, structs-disk_568deb80-fbd8-4c86-9646-a49355ab0d52.xml"
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
-	CREATE_DISK
product:
- Windows
targetos: Windows
req.typenames: CREATE_DISK, *PCREATE_DISK
---

# _CREATE_DISK structure
The CREATE_DISK structure is used with the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff559436">IOCTL_DISK_CREATE_DISK</a>  IOCTL to initialize a disk with an empty partition table. The partition table styles are master boot record (MBR)  or GUID partition table (GPT).

## Syntax
```
typedef struct _CREATE_DISK {
  PARTITION_STYLE PartitionStyle;
  union {
    CREATE_DISK_GPT Gpt;
    CREATE_DISK_MBR Mbr;
  } DUMMYUNIONNAME;
} *PCREATE_DISK, CREATE_DISK;
```

## Members


`PartitionStyle`

Takes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563773">PARTITION_STYLE</a> enumerated value that specifies the type of partition table to use when formatting the disk.

`DUMMYUNIONNAME`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552486">CREATE_DISK_GPT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552490">CREATE_DISK_MBR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559436">IOCTL_DISK_CREATE_DISK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563773">PARTITION_STYLE</a>