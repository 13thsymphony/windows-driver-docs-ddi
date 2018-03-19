---
UID: NS:mountmgr._MOUNTMGR_DRIVE_LETTER_INFORMATION
title: "_MOUNTMGR_DRIVE_LETTER_INFORMATION"
author: windows-driver-content
description: The MOUNTMGR_DRIVE_LETTER_INFORMATION structure is used by the mount manager to furnish a drive letter to a client that has requested a driver letter by means of an IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER request.
old-location: storage\mountmgr_drive_letter_information.htm
old-project: storage
ms.assetid: ad8dc740-c297-43e7-beb9-d93019955fd3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMOUNTMGR_DRIVE_LETTER_INFORMATION, MOUNTMGR_DRIVE_LETTER_INFORMATION, MOUNTMGR_DRIVE_LETTER_INFORMATION structure [Storage Devices], PMOUNTMGR_DRIVE_LETTER_INFORMATION, PMOUNTMGR_DRIVE_LETTER_INFORMATION structure pointer [Storage Devices], _MOUNTMGR_DRIVE_LETTER_INFORMATION, mountmgr/MOUNTMGR_DRIVE_LETTER_INFORMATION, mountmgr/PMOUNTMGR_DRIVE_LETTER_INFORMATION, storage.mountmgr_drive_letter_information, structs-mntmgr_19ece61a-9dda-466c-a414-047d71beeb2c.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mountmgr.h
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
-	mountmgr.h
api_name:
-	MOUNTMGR_DRIVE_LETTER_INFORMATION
product: Windows
targetos: Windows
req.typenames: MOUNTMGR_DRIVE_LETTER_INFORMATION, *PMOUNTMGR_DRIVE_LETTER_INFORMATION
---

# _MOUNTMGR_DRIVE_LETTER_INFORMATION structure
The MOUNTMGR_DRIVE_LETTER_INFORMATION structure is used by the mount manager to furnish a drive letter to a client that has requested a driver letter by means of an <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_next_drive_letter.md">IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER</a> request.

## Syntax
````
typedef struct _MOUNTMGR_DRIVE_LETTER_INFORMATION {
  BOOLEAN DriveLetterWasAssigned;
  UCHAR   CurrentDriveLetter;
} MOUNTMGR_DRIVE_LETTER_INFORMATION, *PMOUNTMGR_DRIVE_LETTER_INFORMATION;
````

## Members


`DriveLetterWasAssigned`

Indicates when <b>TRUE</b> that member <b>CurrentDriveLetter</b> contains a drive letter. When <b>FALSE</b>, a driver letter was not assigned to the device.

`CurrentDriveLetter`

Contains either an existing or a newly assigned drive letter in the form of a single ASCII character (for example, "D") if <b>DriveLetterWasAssigned</b> is <b>TRUE</b>.

## Remarks
For a general discussion of the mount manager and how it communicates with its clients, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mountmgr.h (include Mountmgr.h) |

## See Also

<a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_next_drive_letter.md">IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER</a>