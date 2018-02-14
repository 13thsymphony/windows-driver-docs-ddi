---
UID: NS:ntddstor._STORAGE_READ_CAPACITY
title: "_STORAGE_READ_CAPACITY"
author: windows-driver-content
description: The STORAGE_READ_CAPACITY contains the disk read capacity information returned from a IOCTL_STORAGE_READ_CAPACITIY request.
old-location: storage\storage_read_capacity.htm
old-project: storage
ms.assetid: 891F04C5-277B-4197-942E-68ED21019950
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "_STORAGE_READ_CAPACITY, ntddstor/PSTORAGE_READ_CAPACITY, storage.storage_read_capacity, STORAGE_READ_CAPACITY, PSTORAGE_READ_CAPACITY structure pointer [Storage Devices], PSTORAGE_READ_CAPACITY, ntddstor/STORAGE_READ_CAPACITY, STORAGE_READ_CAPACITY structure [Storage Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddstor.h
apiname:
-	STORAGE_READ_CAPACITY
product: Windows
targetos: Windows
req.typenames: STORAGE_READ_CAPACITY, PSTORAGE_READ_CAPACITY
---

# _STORAGE_READ_CAPACITY structure
The <b>STORAGE_READ_CAPACITY</b> contains the disk read capacity information returned from a <a href="..\ntddstor\ni-ntddstor-ioctl_storage_read_capacity.md">IOCTL_STORAGE_READ_CAPACITIY</a> request.

## Syntax
````
typedef struct _STORAGE_READ_CAPACITY {
  ULONG         Version;
  ULONG         Size;
  ULONG         BlockLength;
  LARGE_INTEGER NumberOfBlocks;
  LARGE_INTEGER DiskLength;
} STORAGE_READ_CAPACITY, *PSTORAGE_READ_CAPACITY;
````

## Members


`BlockLength`

The number of bytes per block on disk.

`DiskLength`

The total disk size in bytes.

`NumberOfBlocks`

The total number of blocks on the disk.

`Size`

The size of this structure. Set to <b>sizeof</b>(STORAGE_READ_CAPACITY).

`Version`

The version of this structure. Set to <b>sizeof</b>(STORAGE_READ_CAPACITY).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_read_capacity.md">IOCTL_STORAGE_READ_CAPACITIY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_READ_CAPACITY structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>