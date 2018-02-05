---
UID : NS:mpiowmi._MPIO_PATH_HEALTH_CLASS
title : "_MPIO_PATH_HEALTH_CLASS"
author : windows-driver-content
description : The MPIO_PATH_HEALTH_CLASS structure represents the health information for a path.
old-location : storage\mpio_path_health_class.htm
old-project : storage
ms.assetid : 13be9014-e1ce-4b08-a264-c2828e8632ae
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : structs-scsibus_ffbf044f-24cd-4e04-8a26-bfa5f2542189.xml, _MPIO_PATH_HEALTH_CLASS, mpiowmi/MPIO_PATH_HEALTH_CLASS, MPIO_PATH_HEALTH_CLASS, PMPIO_PATH_HEALTH_CLASS, mpiowmi/PMPIO_PATH_HEALTH_CLASS, PMPIO_PATH_HEALTH_CLASS structure pointer [Storage Devices], storage.mpio_path_health_class, MPIO_PATH_HEALTH_CLASS structure [Storage Devices], *PMPIO_PATH_HEALTH_CLASS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : mpiowmi.h
req.include-header : Mpiowmi.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.typenames : "*PMPIO_PATH_HEALTH_CLASS, MPIO_PATH_HEALTH_CLASS"
---

# _MPIO_PATH_HEALTH_CLASS structure
The MPIO_PATH_HEALTH_CLASS structure represents the health information for a path.

## Syntax
````
typedef struct _MPIO_PATH_HEALTH_CLASS {
  ULONGLONG PathId;
  ULONGLONG NumberReads;
  ULONGLONG NumberWrites;
  ULONGLONG NumberBytesRead;
  ULONGLONG NumberBytesWritten;
  ULONGLONG NumberRetries;
  ULONGLONG NumberIoErrors;
  ULONGLONG CreateTime;
  ULONGLONG FailTime;
  BOOLEAN   PathOffline;
  UCHAR     NumberReadsWrap;
  UCHAR     NumberWritesWrap;
  UCHAR     NumberBytesReadWrap;
  UCHAR     NumberBytesWrittenWrap;
  UCHAR     OutstandingRequests;
  UCHAR     Pad[2];
} MPIO_PATH_HEALTH_CLASS, *PMPIO_PATH_HEALTH_CLASS;
````

## Members


`CreateTime`

A 64-bit integer that specifies the system time when this instance was created and exposed.

`FailTime`

A 64-bit integer that specifies the system time when the path that is associated with this path ID was removed.

`NumberBytesRead`

An unsigned 64-bitfield that specifies the total number of bytes that are read through the specified path identifier.

`NumberBytesReadWrap`

An unsigned character field that specifies the total number of times the <i>NumberBytesRead</i> parameter has rolled around to zero.

`NumberBytesWritten`

An unsigned 64-bitfield that specifies the total number of bytes that are written through the specified path identifier.

`NumberBytesWrittenWrap`

An unsigned character field that specifies the total number of times that the <i>NumberBytesWritten</i> parameter has rolled around to zero.

`NumberIoErrors`

An unsigned 64-bitfield that specifies the total number of I/O errors that are encountered through the specified path identifier.

`NumberReads`

An unsigned 64-bitfield that specifies the number of read requests that are serviced by the specified path identifier.

`NumberReadsWrap`

An unsigned character field that specifies the total number of times that the <i>NumberReads</i> parameter has rolled around to zero.

`NumberRetries`

An unsigned 64-bitfield that specifies the total number of retries by using the specified path identifier.

`NumberWrites`

An unsigned 64-bitfield that specifies the number of write requests that are serviced by the specified path identifier.

`NumberWritesWrap`

An unsigned character field that specifies the total number of times that the <i>NumberWrites</i> parameter has rolled around to zero.

`OutstandingRequests`

An unsigned character field that specifies the total number of outstanding requests.

`Pad`

Should be zero.

`PathId`

An unsigned 64-bitfield that represents an identifier that is assigned to a particular path.

`PathOffline`

A Boolean field that indicates whether the path that is associated with this path ID is removed.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mpiowmi.h (include Mpiowmi.h) |