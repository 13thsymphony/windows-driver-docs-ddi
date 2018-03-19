---
UID: NF:ntifs.PsUpdateDiskCounters
title: PsUpdateDiskCounters function
author: windows-driver-content
description: The PsUpdateDiskCounters routine updates the disk I/O counters of a given process.
old-location: ifsk\psupdatediskcounters.htm
old-project: ifsk
ms.assetid: 0BDC6629-9C0E-4437-888D-1EF730714CA4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PsUpdateDiskCounters, PsUpdateDiskCounters routine [Installable File System Drivers], ifsk.psupdatediskcounters, ntifs/PsUpdateDiskCounters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsUpdateDiskCounters
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# PsUpdateDiskCounters function
The <b>PsUpdateDiskCounters</b> routine updates the disk I/O counters of a given process.

## Syntax

````
VOID PsUpdateDiskCounters(
   PEPROCESS Process,
   ULONG64   BytesRead,
   ULONG64   BytesWritten,
   ULONG     ReadOperationCount,
   ULONG     WriteOperationCount,
   ULONG     FlushOperationCount
);
````

## Parameters

`Process`

A pointer to the process to update counters for.

`BytesRead`

The number of bytes to update in the Read counter.

`BytesWritten`

The number of bytes to update in the Write counter.

`ReadOperationCount`

The number of read operations to update in the Read Operation counter.

`WriteOperationCount`

The number of write operations to update in the Write Operation counter.

`FlushOperationCount`

The number of flush operations to update in the Flush Operation counter.


## Return Value

This routine does not return a value.

## Remarks

File system drivers use <b>PsUpdateDiskCounters</b> to update counts for disk I/O accounting. A client process can be "charged" the disk I/O counts by the file system.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-psisdiskcountersenabled.md">PsIsDiskCountersEnabled</a>