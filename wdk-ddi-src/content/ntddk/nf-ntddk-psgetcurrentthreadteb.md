---
UID: NF:ntddk.PsGetCurrentThreadTeb
title: PsGetCurrentThreadTeb function
author: windows-driver-content
description: The PsGetCurrentThreadTeb routine returns the Thread Environment Block (TEB) of the current thread. The call must be made in kernel-mode.
old-location: kernel\psgetcurrentthreadteb.htm
old-project: kernel
ms.assetid: 822B75D4-A825-4BB1-8265-A1389F4982C7
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PsGetCurrentThreadTeb, PsGetCurrentThreadTeb routine [Kernel-Mode Driver Architecture], kernel.psgetcurrentthreadteb, ntddk/PsGetCurrentThreadTeb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsGetCurrentThreadTeb
product:
- Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsGetCurrentThreadTeb function
The <b>PsGetCurrentThreadTeb</b> routine returns the Thread Environment Block (TEB) of the current thread. The call must be made in kernel-mode.

## Syntax

```
NTKERNELAPI PVOID PsGetCurrentThreadTeb(

);
```

## Parameters

This function has no parameters.

## Return Value

A pointer to the thread environment block of the current thread. The TEB should be accessed within a try/catch exception block.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559917">Process and Thread Manager Routines</a>