---
UID: NF:wdm.IoInitializeTimer
title: IoInitializeTimer function
author: windows-driver-content
description: The IoInitializeTimer routine sets up a driver-supplied IoTimer routine associated with a given device object.
old-location: kernel\ioinitializetimer.htm
old-project: kernel
ms.assetid: f2b0f74d-7417-443e-96ec-5101b1289f9d
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoInitializeTimer, IoInitializeTimer routine [Kernel-Mode Driver Architecture], k104_28bd2888-4ec7-4de8-b2ea-f006a8f39209.xml, kernel.ioinitializetimer, wdm/IoInitializeTimer
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
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	IoInitializeTimer
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoInitializeTimer function
The <b>IoInitializeTimer</b> routine sets up a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff550381">IoTimer</a> routine associated with a given device object.

## Syntax

```
NTKERNELAPI NTSTATUS IoInitializeTimer(
  PDEVICE_OBJECT         DeviceObject,
  PIO_TIMER_ROUTINE      TimerRoutine,
  __drv_aliasesMem PVOID Context
);
```

## Parameters

`DeviceObject`

Pointer to a device object representing a device on which I/O operations can time out.

`TimerRoutine`

Pointer to the driver-supplied <i>IoTimer</i> routine.

`Context`

Pointer to the driver-determined context with which its <i>IoTimer</i> routine will be called.


## Return Value

<b>IoInitializeTimer</b> returns STATUS_SUCCESS if the <i>IoTimer</i> routine is set up.

## Remarks

<b>IoInitializeTimer</b> should be called only once per device object.

A driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550381">IoTimer</a> routine is called once per second after the driver enables the timer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550373">IoStartTimer</a>. The driver can disable the timer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550377">IoStopTimer</a> and can reenable it again with <b>IoStartTimer</b>.

The driver's <i>IoTimer</i> routine is called at IRQL = DISPATCH_LEVEL and therefore must not contain pageable code.

When the timer is running, the I/O manager calls the driver-supplied <i>IoTimer</i> routine once per second. Drivers whose time-out routines should be called at variable intervals or at intervals of finer granularity can set up a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542983">CustomTimerDpc</a> routine and use the <b>Ke<i>Xxx</i>Timer</b> routines.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550373">IoStartTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550377">IoStopTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550381">IoTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552168">KeInitializeTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553286">KeSetTimer</a>