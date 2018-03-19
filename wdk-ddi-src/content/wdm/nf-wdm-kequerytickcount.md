---
UID: NF:wdm.KeQueryTickCount
title: KeQueryTickCount macro
author: windows-driver-content
description: The KeQueryTickCount routine maintains a count of the interval timer interrupts that have occurred since the system was booted.
old-location: kernel\kequerytickcount.htm
old-project: kernel
ms.assetid: 7cd0ed27-a056-4ed9-8ff4-e917b31b0dd6
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeQueryTickCount, KeQueryTickCount routine [Kernel-Mode Driver Architecture], k105_a6a22896-6f3e-4e58-b443-4a06ff67b0ce.xml, kernel.kequerytickcount, wdm/KeQueryTickCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
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
-	KeQueryTickCount
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeQueryTickCount function
The <b>KeQueryTickCount</b> routine maintains a count of the interval timer interrupts that have occurred since the system was booted.

## Syntax

````
VOID KeQueryTickCount(
  _Out_ PLARGE_INTEGER TickCount
);
````

## Parameters

`CurrentCount`

TBD


## Return Value

None

## Remarks

The <i>TickCount</i> value increases by one at each interval timer interrupt while the system is running.

The preferred method of determining elapsed time is by using <i>TickCount</i> for relative timing and time stamps.

To determine the absolute elapsed time multiply the returned <i>TickCount</i> by the <a href="..\wdm\nf-wdm-kequerytimeincrement.md">KeQueryTimeIncrement</a> return value using compiler support for 64-bit integer operations.

You should not make any assumptions about the length of a tick, because it might vary depending on hardware and other considerations.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-kequeryperformancecounter.md">KeQueryPerformanceCounter</a>



<a href="..\wdm\nf-wdm-kequeryinterrupttime.md">KeQueryInterruptTime</a>



<a href="..\wdm\nf-wdm-kequerytimeincrement.md">KeQueryTimeIncrement</a>