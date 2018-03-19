---
UID: NS:ntddstor._STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR
title: "_STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR"
author: windows-driver-content
description: The output buffer for the StorageDeviceIoCapabilityProperty as defined in STORAGE_PROPERTY_ID.
old-location: storage\storage_device_io_capability_descriptor.htm
old-project: storage
ms.assetid: 98377F8F-62C8-4E8F-838B-A63DC63E4A0C
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PSTORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, PSTORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR structure pointer [Storage Devices], STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR structure [Storage Devices], _STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, ntddstor/PSTORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, ntddstor/STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, storage.storage_device_io_capability_descriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	ntddstor.h
api_name:
-	STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, PSTORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR
---

# _STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR structure
The output buffer for the StorageDeviceIoCapabilityProperty as defined in <a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a>.

## Syntax
````
typedef struct _STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR {
  ULONG Version;
  ULONG Size;
  ULONG LunMaxIoCount;
  ULONG AdapterMaxIoCount;
} STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, *PSTORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR;
````

## Members


`Version`

The version of this structure. The Size serves as the version.

`Size`

The size of this structure.

`LunMaxIoCount`

The logical unit number (LUN) max outstanding I/O count.

`AdapterMaxIoCount`

The adapter max outstanding I/O count.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | ntddstor.h |