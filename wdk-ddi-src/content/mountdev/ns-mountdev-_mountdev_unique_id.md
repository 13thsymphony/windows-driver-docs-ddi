---
UID: NS:mountdev._MOUNTDEV_UNIQUE_ID
title: "_MOUNTDEV_UNIQUE_ID"
author: windows-driver-content
description: The MOUNTDEV_UNIQUE_ID structure contains a unique volume ID that a mount manager client provides to the mount manager in response to an IOCTL_MOUNTDEV_QUERY_UNIQUE_ID request.
old-location: storage\mountdev_unique_id.htm
old-project: storage
ms.assetid: cc6cbda8-4056-41e7-98f9-927a99e66081
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMOUNTDEV_UNIQUE_ID, MOUNTDEV_UNIQUE_ID, MOUNTDEV_UNIQUE_ID structure [Storage Devices], PMOUNTDEV_UNIQUE_ID, PMOUNTDEV_UNIQUE_ID structure pointer [Storage Devices], _MOUNTDEV_UNIQUE_ID, mountdev/MOUNTDEV_UNIQUE_ID, mountdev/PMOUNTDEV_UNIQUE_ID, storage.mountdev_unique_id, structs-mntmgr_424fff73-7b72-4068-b25b-00225f69b159.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mountdev.h
req.include-header: Mountmgr.h
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
-	mountdev.h
api_name:
-	MOUNTDEV_UNIQUE_ID
product: Windows
targetos: Windows
req.typenames: MOUNTDEV_UNIQUE_ID, *PMOUNTDEV_UNIQUE_ID
---

# _MOUNTDEV_UNIQUE_ID structure
The MOUNTDEV_UNIQUE_ID structure contains a unique volume ID that a mount manager client provides to the mount manager in response to an <a href="..\mountdev\ni-mountdev-ioctl_mountdev_query_unique_id.md">IOCTL_MOUNTDEV_QUERY_UNIQUE_ID</a> request.

## Syntax
````
typedef struct _MOUNTDEV_UNIQUE_ID {
  USHORT UniqueIdLength;
  UCHAR  UniqueId[1];
} MOUNTDEV_UNIQUE_ID, *PMOUNTDEV_UNIQUE_ID;
````

## Members


`UniqueIdLength`

Contains the length of the unique volume ID.

`UniqueId`

Contains the unique volume ID as an array of bytes.

## Remarks
For a discussion of unique volume IDs and how the mount manager uses them, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mountdev.h (include Mountmgr.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560443">IOCTL_MOUNTDEV_UNIQUE_ID_CHANGE_NOTIFY</a>