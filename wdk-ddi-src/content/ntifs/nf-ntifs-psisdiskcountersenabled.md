---
UID: NF:ntifs.PsIsDiskCountersEnabled
title: PsIsDiskCountersEnabled function
author: windows-driver-content
description: The enabled state of the per process disk I/O counters is returned by the PsIsDiskCountersEnabled routine.
old-location: ifsk\psisdiskcountersenabled.htm
old-project: ifsk
ms.assetid: E4626CF9-5E76-4C48-9B38-274178E41E30
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PsIsDiskCountersEnabled, PsIsDiskCountersEnabled routine [Installable File System Drivers], ifsk.psisdiskcountersenabled, ntifs/PsIsDiskCountersEnabled
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
req.irql: Any
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsIsDiskCountersEnabled
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# PsIsDiskCountersEnabled function
The enabled state of the per process disk I/O counters is returned by the <b>PsIsDiskCountersEnabled</b> routine.

## Syntax

```
NTKERNELAPI BOOLEAN PsIsDiskCountersEnabled(

);
```

## Parameters

This function has no parameters.

## Return Value

If TRUE, the disk

## Remarks

A file system driver uses the <b>PsIsDiskCountersEnabled</b> routine to query the system enabled  state of the disk I/O  counters. A file system driver will use this routine prior to accounting for process disk I/O using <a href="https://msdn.microsoft.com/library/windows/hardware/hh971609">PsUpdateDiskCounters</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh971609">PsUpdateDiskCounters</a>