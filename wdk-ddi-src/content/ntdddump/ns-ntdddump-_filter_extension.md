---
UID : NS:ntdddump._FILTER_EXTENSION
title : "_FILTER_EXTENSION"
author : windows-driver-content
description : The crash dump driver passes a pointer to a FILTER_EXTENSION structure when the filter driver callback routines are called.
old-location : storage\filter_extension.htm
old-project : storage
ms.assetid : 1113e917-3273-4ba7-8702-fe90a22fb024
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : "*PFILTER_EXTENSION, PFILTER_EXTENSION structure pointer [Storage Devices], storage.filter_extension, PFILTER_EXTENSION, ntdddump/FILTER_EXTENSION, FILTER_EXTENSION structure [Storage Devices], ntdddump/PFILTER_EXTENSION, FILTER_EXTENSION, structs-filter_c9e640bb-9678-4e2f-9341-0d26b36e65e6.xml, _FILTER_EXTENSION"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntdddump.h
req.include-header : Ntdddump.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows Vista and Windows Server 2008.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PFILTER_EXTENSION, FILTER_EXTENSION"
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


`DeviceObject`

A pointer to the device object of the dump volume. This pointer points to the top of the dump volume stack.

`DiskSize`

Size of the disk.

`DumpData`

A pointer to the context data that is provided by the filter driver in <a href="..\ntdddump\ns-ntdddump-_filter_initialization_data.md">FILTER_INITIALIZATION_DATA</a>.

`DumpType`

This parameter indicates the type of dump that this instance of the filter driver is loaded on.

`Flags`



`Geometry`

The disk geometry of the dump device in <a href="..\ntdddisk\ns-ntdddisk-_disk_geometry.md">DISK_GEOMETRY</a> format.

`PartitionInfo`

The partition information in <a href="..\ntdddisk\ns-ntdddisk-_disk_partition_info.md">DISK_PARTITION_INFO</a> format.

`Size`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista and Windows Server 2008. Available starting with Windows Vista and Windows Server 2008. |
| **Header** | ntdddump.h (include Ntdddump.h) |

## See Also

<a href="..\ntdddisk\ns-ntdddisk-_disk_partition_info.md">DISK_PARTITION_INFO</a>

<a href="..\ntdddisk\ns-ntdddisk-_disk_geometry.md">DISK_GEOMETRY</a>

<a href="..\ntdddump\ns-ntdddump-_filter_initialization_data.md">FILTER_INITIALIZATION_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FILTER_EXTENSION structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>