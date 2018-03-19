---
UID: NF:ntddk.PsGetCurrentThreadId
title: PsGetCurrentThreadId function
author: windows-driver-content
description: The PsGetCurrentThreadId routine identifies the current thread.
old-location: kernel\psgetcurrentthreadid.htm
old-project: kernel
ms.assetid: c4da1dcb-435d-4e32-8114-3b0ae4352000
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PsGetCurrentThreadId, PsGetCurrentThreadId routine [Kernel-Mode Driver Architecture], k108_eae0d8bf-f2fe-49dd-b3b7-6da9114f844a.xml, kernel.psgetcurrentthreadid, ntddk/PsGetCurrentThreadId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
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
-	PsGetCurrentThreadId
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsGetCurrentThreadId function
The <b>PsGetCurrentThreadId</b> routine identifies the current thread.

## Syntax

````
HANDLE PsGetCurrentThreadId(void);
````

## Parameters

This function has no parameters.

## Return Value

The <b>PsGetCurrentThreadId</b> routine returns the thread ID of the current thread.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\ntddk\nf-ntddk-psgetcurrentprocessid.md">PsGetCurrentProcessId</a>



<a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutine.md">PsSetCreateThreadNotifyRoutine</a>



<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>



<a href="..\wdm\nf-wdm-kegetcurrentthread.md">KeGetCurrentThread</a>