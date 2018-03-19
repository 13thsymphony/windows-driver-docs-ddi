---
UID: NS:ntddstor._DEVICE_COPY_OFFLOAD_DESCRIPTOR
title: "_DEVICE_COPY_OFFLOAD_DESCRIPTOR"
author: windows-driver-content
description: Used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to describe the copy offload capabilities of a storage device.
old-location: storage\device_copy_offload_descriptor.htm
old-project: storage
ms.assetid: 192684D1-3D01-4EAA-989F-2E21E7187B3B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDEVICE_COPY_OFFLOAD_DESCRIPTOR, DEVICE_COPY_OFFLOAD_DESCRIPTOR, DEVICE_COPY_OFFLOAD_DESCRIPTOR structure [Storage Devices], PDEVICE_COPY_OFFLOAD_DESCRIPTOR, PDEVICE_COPY_OFFLOAD_DESCRIPTOR structure pointer [Storage Devices], _DEVICE_COPY_OFFLOAD_DESCRIPTOR, ntddstor/DEVICE_COPY_OFFLOAD_DESCRIPTOR, ntddstor/PDEVICE_COPY_OFFLOAD_DESCRIPTOR, storage.device_copy_offload_descriptor"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	DEVICE_COPY_OFFLOAD_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: DEVICE_COPY_OFFLOAD_DESCRIPTOR, *PDEVICE_COPY_OFFLOAD_DESCRIPTOR
---

# _DEVICE_COPY_OFFLOAD_DESCRIPTOR structure
Used in conjunction with the 
   <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to describe the copy offload capabilities of a storage device.

## Syntax
````
typedef struct _DEVICE_COPY_OFFLOAD_DESCRIPTOR {
  ULONG      Version;
  ULONG      Size;
  ULONG      MaximumTokenLifetime;
  ULONG      DefaultTokenLifetime;
  ULONGULONG MaximumTransferSize;
  ULONGULONG OptimalTransferCount;
  ULONG      MaximumDataDescriptors;
  ULONG      MaximumTransferLengthPerDescriptor;
  ULONG      OptimalTransferLengthPerDescriptor;
  USHORT     OptimalTransferLengthGranularity;
  UCHAR      Reserved[2];
} DEVICE_COPY_OFFLOAD_DESCRIPTOR, *PDEVICE_COPY_OFFLOAD_DESCRIPTOR;
````

## Members


`Version`

Contains the size of this structure, in bytes. The value of this member will change as members are added to 
      the structure.

`Size`

Specifies the total size of the data returned, in bytes. This may include data that follows this 
      structure.

`MaximumTokenLifetime`

The maximum lifetime of the token, in seconds.

`DefaultTokenLifetime`

The default lifetime of the token, in seconds.

`MaximumTransferSize`

The maximum transfer size, in bytes.

`OptimalTransferCount`

The optimal transfer size, in bytes.

`MaximumDataDescriptors`

The maximum number of data descriptors.

`MaximumTransferLengthPerDescriptor`

The maximum transfer length, in blocks, per descriptor.

`OptimalTransferLengthPerDescriptor`

The optimal transfer length, in blocks, per descriptor.

`OptimalTransferLengthGranularity`

The granularity of the optimal transfer length, in blocks. Transfer lengths that are not an even multiple 
      of this length may be delayed.

`Reserved`

Reserved for future use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>