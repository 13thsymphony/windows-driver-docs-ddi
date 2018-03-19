---
UID: NS:ntdddump._FILTER_EXTENSION
title: "_FILTER_EXTENSION"
author: windows-driver-content
description: The crash dump driver passes a pointer to a FILTER_EXTENSION structure when the filter driver callback routines are called.
old-location: storage\filter_extension.htm
old-project: storage
ms.assetid: 1113e917-3273-4ba7-8702-fe90a22fb024
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFILTER_EXTENSION, FILTER_EXTENSION, FILTER_EXTENSION structure [Storage Devices], PFILTER_EXTENSION, PFILTER_EXTENSION structure pointer [Storage Devices], _FILTER_EXTENSION, ntdddump/FILTER_EXTENSION, ntdddump/PFILTER_EXTENSION, storage.filter_extension, structs-filter_c9e640bb-9678-4e2f-9341-0d26b36e65e6.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddump.h
req.include-header: Ntdddump.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista and Windows Server 2008.
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
-	ntdddump.h
api_name:
-	FILTER_EXTENSION
product: Windows
targetos: Windows
req.typenames: FILTER_EXTENSION, *PFILTER_EXTENSION
---

# _FILTER_EXTENSION structure
The crash dump driver passes a pointer to a FILTER_EXTENSION structure when the filter driver callback routines are called.

## Syntax
````
typedef struct _FILTER_EXTENSION {
  FILTER_DUMP_TYPE    DumpType;
  PDEVICE_OBJECT      DeviceObject;
  DISK_GEOMETRY       Geometry;
  LARGE_INTEGER       DiskSize;
  DISK_PARTITION_INFO PartitionInfo;
  PVOID               DumpData;
} FILTER_EXTENSION, *PFILTER_EXTENSION;
````

## Members


`DumpType`

This parameter indicates the type of dump that this instance of the filter driver is loaded on.

`DeviceObject`

A pointer to the device object of the dump volume. This pointer points to the top of the dump volume stack.

`Geometry`

The disk geometry of the dump device in <a href="..\ntdddisk\ns-ntdddisk-_disk_geometry.md">DISK_GEOMETRY</a> format.

`DiskSize`

Size of the disk.

`PartitionInfo`

The partition information in <a href="..\ntdddisk\ns-ntdddisk-_disk_partition_info.md">DISK_PARTITION_INFO</a> format.

`DumpData`

A pointer to the context data that is provided by the filter driver in <a href="..\ntdddump\ns-ntdddump-_filter_initialization_data.md">FILTER_INITIALIZATION_DATA</a>.

`Size`



`Flags`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista and Windows Server 2008. Available starting with Windows Vista and Windows Server 2008. |
| **Header** | ntdddump.h (include Ntdddump.h) |

## See Also

<a href="..\ntdddump\ns-ntdddump-_filter_initialization_data.md">FILTER_INITIALIZATION_DATA</a>



<a href="..\ntdddisk\ns-ntdddisk-_disk_partition_info.md">DISK_PARTITION_INFO</a>



<a href="..\ntdddisk\ns-ntdddisk-_disk_geometry.md">DISK_GEOMETRY</a>