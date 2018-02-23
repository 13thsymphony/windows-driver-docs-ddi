---
UID: NS:mpiowmi._MPIO_DRIVE_INFO
title: "_MPIO_DRIVE_INFO"
author: windows-driver-content
description: The MPIO_DRIVE_INFO structure represents a multi-path disk in the system.
old-location: storage\mpio_drive_info.htm
old-project: storage
ms.assetid: 38d79fae-9701-4e92-bf73-4732e02c17ab
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MPIO_DRIVE_INFO, structs-scsibus_307e7c06-15cc-4d25-9cd6-115370e20036.xml, *PMPIO_DRIVE_INFO, MPIO_DRIVE_INFO structure [Storage Devices], storage.mpio_drive_info, mpiowmi/PMPIO_DRIVE_INFO, _MPIO_DRIVE_INFO, mpiowmi/MPIO_DRIVE_INFO, PMPIO_DRIVE_INFO structure pointer [Storage Devices], PMPIO_DRIVE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mpiowmi.h
apiname:
-	MPIO_DRIVE_INFO
product: Windows
targetos: Windows
req.typenames: MPIO_DRIVE_INFO, *PMPIO_DRIVE_INFO
---

# _MPIO_DRIVE_INFO structure
The MPIO_DRIVE_INFO structure represents a multi-path disk in the system.

## Syntax
````
typedef struct _MPIO_DRIVE_INFO {
  ULONG NumberPaths;
  WCHAR Name[63 + 1];
  WCHAR SerialNumber[63 + 1];
  WCHAR DsmName[63 + 1];
} MPIO_DRIVE_INFO, *PMPIO_DRIVE_INFO;
````

## Members


`DsmName`

A string field (of maximum length 63 characters) that returns the friendly name of the controlling DSM for the device.

`Name`

A string field (of maximum length 63 characters) that returns the device name that was created by MPIO for the LUN.

`NumberPaths`

An unsigned 32-bitfield that represents the number of paths to the LUN.

`SerialNumber`

A string field (of maximum length 63 characters) that returns the serial number that was created for the LUN by either the DSM or by MPIO itself.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mpiowmi.h (include Mpiowmi.h) |