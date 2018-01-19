---
UID : NF:ntifs.FsRtlRemoveDotsFromPath
title : FsRtlRemoveDotsFromPath function
author : windows-driver-content
description : The FsRtlRemoveDotsFromPath routine removes unnecessary occurrences of '.' and '..' from the specified path.
old-location : ifsk\fsrtlremovedotsfrompath.htm
old-project : ifsk
ms.assetid : af6ecdb7-8713-460d-8fd9-ef027ac15b39
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FsRtlRemoveDotsFromPath
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : FltKernel.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FsRtlRemoveDotsFromPath
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
req.typenames : TOKEN_TYPE
---


# FsRtlRemoveDotsFromPath function
The <b>FsRtlRemoveDotsFromPath</b> routine removes unnecessary occurrences of '.' and '..' from the specified path.

## Syntax

````
NTSTATUS FsRtlRemoveDotsFromPath(
  _Inout_ PWSTR  OriginalString,
  _In_    USHORT PathLength,
  _Out_   USHORT *NewLength
);
````

## Parameters

`OriginalString`

A pointer to the buffer to be processed.

`PathLength`

The length of buffer (in bytes).

`NewLength`

A pointer to the new length of the buffer, after processing.


## Return Value

The<b> FsRtlRemoveDotsFromPath</b> routine returns either STATUS_SUCCESS value for success or STATUS_IO_REPARSE_DATA_INVALID if the operation could not be completed.

## Remarks

This routine would take a path as <i>OriginalString</i> like the following example:

The routine would modify <i>OriginalString</i> as follows:

The routine will fail with STATUS_IO_REPARSE_DATA_INVALID if any of the following strings are passed as <i>OriginalString</i>:</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include FltKernel.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |