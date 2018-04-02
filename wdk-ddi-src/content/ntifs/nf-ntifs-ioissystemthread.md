---
UID: NF:ntifs.IoIsSystemThread
title: IoIsSystemThread function
author: windows-driver-content
description: The IoIsSystemThread routine checks whether a given thread is a system thread.
old-location: ifsk\ioissystemthread.htm
old-project: ifsk
ms.assetid: 1f3dc15f-14b5-4797-83be-ba3a01a1551b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IoIsSystemThread, IoIsSystemThread routine [Installable File System Drivers], ifsk.ioissystemthread, ioref_3e14f3af-c985-43a4-bc57-927483597c79.xml, ntifs/IoIsSystemThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
-	IoIsSystemThread
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoIsSystemThread function
The <b>IoIsSystemThread</b> routine checks whether a given thread is a system thread.

## Syntax

```
NTKERNELAPI BOOLEAN IoIsSystemThread(
  PETHREAD Thread
);
```

## Parameters

`Thread`

Pointer to the thread to be checked.


## Return Value

<b>IoIsSystemThread</b> returns <b>TRUE</b> if the specified thread is a system thread, otherwise <b>FALSE</b>.

## Remarks

For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://msdn.microsoft.com/fbd8aadd-5a24-48c9-9865-80cc7dc97316">Driver Threads, Dispatcher Objects, and Resources</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559945">PsIsSystemThread</a>