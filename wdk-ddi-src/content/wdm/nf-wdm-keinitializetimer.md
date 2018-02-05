---
UID : NF:wdm.KeInitializeTimer
title : KeInitializeTimer function
author : windows-driver-content
description : The KeInitializeTimer routine initializes a timer object.
old-location : kernel\keinitializetimer.htm
old-project : kernel
ms.assetid : 97140cf6-9c5a-4fdc-b7c7-10e6d28b9b1b
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : k105_ce90de5c-7259-4863-adf1-fe90f288e791.xml, wdm/KeInitializeTimer, kernel.keinitializetimer, KeInitializeTimer, KeInitializeTimer routine [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : IrqlKeDispatchLte, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : "<= DISPATCH_LEVEL (see Remarks section)"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# KeInitializeTimer function
The <b>KeInitializeTimer</b> routine initializes a timer object.

## Syntax

````
VOID KeInitializeTimer(
  _Out_ PKTIMER Timer
);
````

## Parameters

`Timer`

Pointer to a timer object, for which the caller provides the storage.


## Return Value

None

## Remarks

The timer object is initialized to a not-signaled state.

Storage for a timer object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

<b>KeInitializeTimer</b> can only initialize a notification timer. Use <a href="..\wdm\nf-wdm-keinitializetimerex.md">KeInitializeTimerEx</a> to initialize a notification timer or a synchronization timer.

Use <a href="..\wdm\nf-wdm-kesettimer.md">KeSetTimer</a> or <a href="..\wdm\nf-wdm-kesettimerex.md">KeSetTimerEx</a> to define when the timer will expire.

For more information about timer objects, see <a href="https://msdn.microsoft.com/b58487de-6e9e-45f4-acb8-9233c8718ee2">Timer Objects and DPCs</a>.

Callers of <b>KeInitializeTimer</b> should be running at IRQL = DISPATCH_LEVEL or lower. It is best to initialize timers at IRQL = PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL (see Remarks section)" |
| **DDI compliance rules** | IrqlKeDispatchLte, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>

<a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a>

<a href="..\wdm\nf-wdm-kecanceltimer.md">KeCancelTimer</a>

<a href="..\wdm\nf-wdm-keinitializetimerex.md">KeInitializeTimerEx</a>

<a href="..\wdm\nf-wdm-kesettimer.md">KeSetTimer</a>

<a href="..\wdm\nf-wdm-kesettimerex.md">KeSetTimerEx</a>

<a href="..\wdm\nf-wdm-kereadstatetimer.md">KeReadStateTimer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeInitializeTimer routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>