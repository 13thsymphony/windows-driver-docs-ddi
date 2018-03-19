---
UID: NF:wdm.IoGetCurrentProcess
title: IoGetCurrentProcess function
author: windows-driver-content
description: The IoGetCurrentProcess routine returns a pointer to the current process.
old-location: kernel\iogetcurrentprocess.htm
old-project: kernel
ms.assetid: 97a5c14f-949a-4455-9109-79355e5dec37
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoGetCurrentProcess, IoGetCurrentProcess routine [Kernel-Mode Driver Architecture], k104_f59c640e-e335-46e0-a6ca-2f672bb6fc35.xml, kernel.iogetcurrentprocess, wdm/IoGetCurrentProcess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
-	IoGetCurrentProcess
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoGetCurrentProcess function
The <b>IoGetCurrentProcess</b> routine returns a pointer to the current process.

## Syntax

````
PEPROCESS  IoGetCurrentProcess(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>IoGetCurrentProcess</b> returns a pointer to the current process.

## Remarks

This routine is identical to <a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>