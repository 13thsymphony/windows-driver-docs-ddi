---
UID: NS:ntdddisk._DRIVERSTATUS
title: "_DRIVERSTATUS"
author: windows-driver-content
description: The DRIVERSTATUS structure is used in conjunction with the SENDCMDOUTPARAMS structure and the SMART_SEND_DRIVE_COMMAND request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.
old-location: storage\driverstatus.htm
old-project: storage
ms.assetid: de97322f-a756-49a8-a6e6-dab42f278388
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*LPDRIVERSTATUS, *PDRIVERSTATUS, DRIVERSTATUS, DRIVERSTATUS structure [Storage Devices], LPDRIVERSTATUS, LPDRIVERSTATUS structure pointer [Storage Devices], PDRIVERSTATUS, PDRIVERSTATUS structure pointer [Storage Devices], _DRIVERSTATUS, ntdddisk/DRIVERSTATUS, ntdddisk/LPDRIVERSTATUS, ntdddisk/PDRIVERSTATUS, storage.driverstatus, structs-IDE_e49310ff-1d3c-44d5-a997-08b8f500ed13.xml"
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
-	DRIVERSTATUS
product:
- Windows
targetos: Windows
req.typenames: DRIVERSTATUS, *PDRIVERSTATUS, *LPDRIVERSTATUS
---

# _DRIVERSTATUS structure
The DRIVERSTATUS structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565405">SENDCMDOUTPARAMS</a> structure and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a> request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.

## Syntax
```
typedef struct _DRIVERSTATUS {
  UCHAR bDriverError;
  UCHAR bIDEError;
  UCHAR bReserved[2];
  ULONG dwReserved[2];
} *PDRIVERSTATUS, *LPDRIVERSTATUS, DRIVERSTATUS;
```

## Members


`bDriverError`

Error code from driver, or 0 if no error.

`bIDEError`

Contents of IDE Error register.

`bReserved`

Reserved.

`dwReserved`

Reserved.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565405">SENDCMDOUTPARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a>