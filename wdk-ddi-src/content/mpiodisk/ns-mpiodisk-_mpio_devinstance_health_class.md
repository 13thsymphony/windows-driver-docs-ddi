---
UID: NS:mpiodisk._MPIO_DEVINSTANCE_HEALTH_CLASS
title: "_MPIO_DEVINSTANCE_HEALTH_CLASS"
author: windows-driver-content
description: The MPIO_DEVINSTANCE_HEALTH_CLASS structure holds the health information for a instance of a device exposed through the specified path identifiers.
old-location: storage\mpio_devinstance_health_class.htm
old-project: storage
ms.assetid: 6d0afab5-4aba-4ebc-a864-85c83cf464d0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMPIO_DEVINSTANCE_HEALTH_CLASS, MPIO_DEVINSTANCE_HEALTH_CLASS, MPIO_DEVINSTANCE_HEALTH_CLASS structure [Storage Devices], PMPIO_DEVINSTANCE_HEALTH_CLASS, PMPIO_DEVINSTANCE_HEALTH_CLASS structure pointer [Storage Devices], _MPIO_DEVINSTANCE_HEALTH_CLASS, mpiodisk/MPIO_DEVINSTANCE_HEALTH_CLASS, mpiodisk/PMPIO_DEVINSTANCE_HEALTH_CLASS, storage.mpio_devinstance_health_class, structs-scsibus_aae91588-5920-42bb-8c74-13604bed0bfc.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiodisk.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mpiodisk.h
api_name:
-	MPIO_DEVINSTANCE_HEALTH_CLASS
product:
- Windows
targetos: Windows
req.typenames: MPIO_DEVINSTANCE_HEALTH_CLASS, *PMPIO_DEVINSTANCE_HEALTH_CLASS
---

# _MPIO_DEVINSTANCE_HEALTH_CLASS structure
The MPIO_DEVINSTANCE_HEALTH_CLASS structure holds the health information for a instance of a device exposed through the specified path identifiers.

## Syntax
```
typedef struct _MPIO_DEVINSTANCE_HEALTH_CLASS {
  ULONGLONG PathId;
  ULONGLONG NumberReads;
  ULONGLONG NumberWrites;
  ULONGLONG NumberBytesRead;
  ULONGLONG NumberBytesWritten;
  ULONGLONG NumberRetries;
  ULONGLONG NumberIoErrors;
  ULONGLONG CreateTime;
  ULONGLONG FailTime;
  BOOLEAN   DeviceOffline;
  UCHAR     NumberReadsWrap;
  UCHAR     NumberWritesWrap;
  UCHAR     NumberBytesReadWrap;
  UCHAR     NumberBytesWrittenWrap;
  UCHAR     Pad[3];
} MPIO_DEVINSTANCE_HEALTH_CLASS, *PMPIO_DEVINSTANCE_HEALTH_CLASS;
```

## Members


`PathId`

An unsigned 64-bitfield that returns the path identifier that is associated with this instance of a multi-path disk.

`NumberReads`

An unsigned 64-bitfield that specifies the number of read requests that are serviced by the specified path identifier.

`NumberWrites`

An unsigned 64-bitfield that specifies the number of write requests that are serviced by the specified path identifier

`NumberBytesRead`

An unsigned 64-bitfield that specifies the total number of bytes that are read through the specified path identifier

`NumberBytesWritten`

An unsigned 64-bitfield that specifies the total number of bytes that are written through the specified path identifier.

`NumberRetries`

An unsigned 64-bitfield that specifies the total number of retries through the specified path identifier.

`NumberIoErrors`

An unsigned 64-bitfield that specifies the total number of I/O errors that are encountered through the specified path identifier.

`CreateTime`

A 64-bit integer that specifies the system time when this instance was created and exposed.

`FailTime`

A 64-bit integer that specifies the system time when the path associated with this path ID was removed.

`DeviceOffline`

A Boolean field that indicates whether the path associated with this path ID has been removed.

`NumberReadsWrap`

An unsigned character field that specifies the total number of times the <i>NumberReads</i> parameter has rolled around to zero.

`NumberWritesWrap`

An unsigned character field that specifies the total number of times the <i>NumberWrites</i> parameter has rolled around to zero.

`NumberBytesReadWrap`

An unsigned character field that specifies the total number of times the <i>NumberBytesRead</i> parameter has rolled around to zero.

`NumberBytesWrittenWrap`

An unsigned character field that specifies the total number of times the <i>NumberBytesWritten</i> parameter has rolled around to zero.

`Pad`

Should be zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mpiodisk.h (include Mpiowmi.h) |