---
UID: NF:ntifs.PsGetCurrentThread
title: PsGetCurrentThread function
author: windows-driver-content
description: The PsGetCurrentThread routine identifies the current thread.
old-location: kernel\psgetcurrentthread.htm
old-project: kernel
ms.assetid: 132b30fe-21ef-48dc-8c69-02ccac563b87
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExGetCurrentResourceThread, PsGetCurrentThread, PsGetCurrentThread routine [Kernel-Mode Driver Architecture], k108_75fb6f47-8a13-4f2c-9b94-a8b7125bbcb6.xml, kernel.psgetcurrentthread, wdm/PsGetCurrentThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
-	PsGetCurrentThread
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# PsGetCurrentThread function
The <b>PsGetCurrentThread</b> routine identifies the current thread.

## Syntax

```
CFORCEINLINE PETHREAD PsGetCurrentThread(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>PsGetCurrentThread</b> returns a pointer to the executive thread object that represents the currently executing thread.

## Remarks

This macro

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552084">KeGetCurrentThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559932">PsCreateSystemThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559935">PsGetCurrentProcessId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559945">PsIsSystemThread</a>