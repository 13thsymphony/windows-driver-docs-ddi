---
UID: NF:wdm.ExRaiseStatus
title: ExRaiseStatus function
author: windows-driver-content
description: The ExRaiseStatus routine is called by drivers that supply structured exception handlers to handle particular errors that occur while they are processing I/O requests.
old-location: kernel\exraisestatus.htm
old-project: kernel
ms.assetid: eefbec75-f441-492b-becb-98434253dd62
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExRaiseStatus, ExRaiseStatus routine [Kernel-Mode Driver Architecture], k102_b188a166-f1f1-49bd-8195-aa72f86ca177.xml, kernel.exraisestatus, wdm/ExRaiseStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExPassive, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExRaiseStatus
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExRaiseStatus function
The <b>ExRaiseStatus</b> routine is called by drivers that supply structured exception handlers to handle particular errors that occur while they are processing I/O requests.

## Syntax

```
NTKERNELAPI DECLSPEC_NORETURN VOID ExRaiseStatus(
  NTSTATUS Status
);
```

## Parameters

`Status`

Specifies one of the system-defined STATUS_<i>XXX</i> values.


## Return Value

None

## Remarks

Highest-level drivers, particularly file systems, can call <b>ExRaiseStatus</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<=APC_LEVEL" |
| **DDI compliance rules** | IrqlExPassive, HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545509">ExRaiseAccessViolation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545524">ExRaiseDatatypeMisalignment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548245">IoAllocateErrorLogEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551961">KeBugCheckEx</a>