---
UID: NS:wdm._FILE_FULL_EA_INFORMATION
title: "_FILE_FULL_EA_INFORMATION"
author: windows-driver-content
description: The FILE_FULL_EA_INFORMATION structure provides extended attribute (EA) information. This structure is used primarily by network drivers.
old-location: kernel\file_full_ea_information.htm
old-project: kernel
ms.assetid: 1b9bbb6a-2dfb-4f3f-8083-62b51a62dec6
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PFILE_FULL_EA_INFORMATION, FILE_FULL_EA_INFORMATION, FILE_FULL_EA_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_FULL_EA_INFORMATION, PFILE_FULL_EA_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_FULL_EA_INFORMATION, kernel.file_full_ea_information, kstruct_b_3640566d-def9-44eb-a205-a6361d46e246.xml, wdm/FILE_FULL_EA_INFORMATION, wdm/PFILE_FULL_EA_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	FILE_FULL_EA_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_FULL_EA_INFORMATION, *PFILE_FULL_EA_INFORMATION
req.product: Windows 10 or later.
---

# _FILE_FULL_EA_INFORMATION structure
The <b>FILE_FULL_EA_INFORMATION</b> structure provides extended attribute (EA) information. This structure is used primarily by network drivers.

## Syntax
````
typedef struct _FILE_FULL_EA_INFORMATION {
  ULONG  NextEntryOffset;
  UCHAR  Flags;
  UCHAR  EaNameLength;
  USHORT EaValueLength;
  CHAR   EaName[1];
} FILE_FULL_EA_INFORMATION, *PFILE_FULL_EA_INFORMATION;
````

## Members


`NextEntryOffset`

The offset of the next <b>FILE_FULL_EA_INFORMATION</b>-type entry. This member is zero if no other entries follow this one.

`Flags`

Can be zero or can be set with FILE_NEED_EA, indicating that the file to which the EA belongs cannot be interpreted without understanding the associated extended attributes.

`EaNameLength`

The length in bytes of the <b>EaName</b> array. This value does not include a null-terminator to <b>EaName</b>.

`EaValueLength`

The length in bytes of each EA value in the array.

`EaName`

An array of characters naming the EA for this entry.

## Remarks
This structure is longword-aligned. If a set of <b>FILE_FULL_EA_INFORMATION</b> entries is buffered, <b>NextEntryOffset</b> value in each entry, except the last, falls on a longword boundary. 

The value(s) associated with each entry follows the <b>EaName</b> array. That is, an EA's values are located at <b>EaName</b> + (<b>EaNameLength</b> + 1).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>