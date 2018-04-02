---
UID: NF:ntifs.FsRtlIncrementCcFastReadNoWait
title: FsRtlIncrementCcFastReadNoWait function
author: windows-driver-content
description: The FsRtlIncrementCcFastReadNoWait routine increments the CcFastReadNoWait performance counter in a per processor control block of cache manager system counters.
old-location: ifsk\fsrtlincrementccfastreadnowait.htm
old-project: ifsk
ms.assetid: 14a1b22a-5d1b-4da6-9610-396fa128ce01
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlIncrementCcFastReadNoWait, FsRtlIncrementCcFastReadNoWait routine [Installable File System Drivers], fsrtlref_f72704ce-84b6-4201-a727-b97fd70accfd.xml, ifsk.fsrtlincrementccfastreadnowait, ntifs/FsRtlIncrementCcFastReadNoWait
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlIncrementCcFastReadNoWait
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlIncrementCcFastReadNoWait function
The <b>FsRtlIncrementCcFastReadNoWait</b> routine increments the CcFastReadNoWait performance counter in a per processor control block of cache manager system counters.

## Syntax

```
NTKERNELAPI VOID FsRtlIncrementCcFastReadNoWait(

);
```

## Parameters

This function has no parameters.

## Return Value

This routine does not return a value.

## Remarks

<b>FsRtlIncrementCcFastReadNoWait</b> increments the CcFastReadNoWait performance counter in the per processor control block of cache manager system counters. This counter indicates that a fast I/O read operation, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545791">FsRtlCopyRead</a>, was called with the <i>Wait</i> parameter set to <b>FALSE</b> indicating that the caller cannot be put into a wait state until all the data has been copied.

File system drivers should call this function to update the performance counter if the driver chooses to override the default fast I/O read handler.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This routine is available on Microsoft Windows XP and later.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545791">FsRtlCopyRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546078">FsRtlIncrementCcFastReadNotPossible</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546091">FsRtlIncrementCcFastReadResourceMiss</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546096">FsRtlIncrementCcFastReadWait</a>