---
UID: NF:ntddk.KeSetBasePriorityThread
title: KeSetBasePriorityThread function
author: windows-driver-content
description: The KeSetBasePriorityThread routine sets the run-time priority, relative to the current process, for a given thread.
old-location: kernel\kesetbaseprioritythread.htm
old-project: kernel
ms.assetid: 7070070c-a953-4120-bddf-c1a7f080ef50
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeSetBasePriorityThread, KeSetBasePriorityThread routine [Kernel-Mode Driver Architecture], k105_6c558266-e459-447c-9586-4b327e24d7dd.xml, kernel.kesetbaseprioritythread, ntddk/KeSetBasePriorityThread
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeSetBasePriorityThread
product:
- Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# KeSetBasePriorityThread function
The <b>KeSetBasePriorityThread</b> routine sets the run-time priority, relative to the current process, for a given thread.

## Syntax

```
NTKERNELAPI LONG KeSetBasePriorityThread(
  PKTHREAD Thread,
  LONG     Increment
);
```

## Parameters

`Thread`

Pointer to a dispatcher object of type KTHREAD.

`Increment`

Specifies the value to be added to the base priority of the process for the <i>Thread</i>.


## Return Value

<b>KeSetBasePriorityThread</b> returns the previous base priority increment of the given thread. The previous base priority increment is defined as the difference between the specified thread's old base priority and the base priority of the thread's process.

## Remarks

The new base priority is computed by adding the given <i>Increment</i>, which can be a negative value, to the base priority of the specified thread's process. The resultant value is stored as the base priority of the specified thread.

Drivers that set up device-dedicated threads with variable priority attributes can call this routine to set such a thread's priority relative to the system process in which the thread is created.

The new base priority is restricted to the priority class of the given thread's process. Therefore, the base priority is not allowed to cross over from a variable priority class to a real-time priority class or vice versa.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552084">KeGetCurrentThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553062">KeQueryPriorityThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553265">KeSetPriorityThread</a>