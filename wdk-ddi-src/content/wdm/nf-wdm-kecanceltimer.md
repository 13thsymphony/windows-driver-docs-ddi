---
UID : NF:wdm.KeCancelTimer
title : KeCancelTimer function
author : windows-driver-content
description : The KeCancelTimer routine dequeues a timer object before the timer interval, if any was set, expires.
old-location : kernel\kecanceltimer.htm
old-project : kernel
ms.assetid : aefbf6d6-c107-4bf2-993d-d7ba8ea7ffcd
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : k105_89adf0ea-9f6b-4e21-be3a-7f75f1baec10.xml, KeCancelTimer routine [Kernel-Mode Driver Architecture], KeCancelTimer, kernel.kecanceltimer, wdm/KeCancelTimer
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
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# KeCancelTimer function
The <b>KeCancelTimer</b> routine dequeues a timer object before the timer interval, if any was set, expires.

## Syntax

````
BOOLEAN KeCancelTimer(
  _Inout_ PKTIMER Timer
);
````

## Parameters

This function has no parameters.

## Return Value

If the specified timer object is in the system timer queue, <b>KeCancelTimer</b> returns <b>TRUE</b>.

## Remarks

If the timer object is currently in the system timer queue, it is removed from the queue. If a DPC object is associated with the timer, it too is canceled. Otherwise, no operation is performed.

The routine returns <b>TRUE</b> if the timer is still in the timer queue. A nonperiodic timer is removed from the system queue as soon as it expires. Thus, for nonperiodic timers, <b>KeCancelTimer</b> returns <b>FALSE</b> if the timer DPC has been queued. Periodic timers are always in the timer queue, so <b>KeCancelTimer</b> always returns <b>TRUE</b> for periodic timers. 

Note that a DPC that is already running runs to completion. The driver must ensure that the DPC has completed before freeing any resources used by the DPC. For a nonperiodic timer, you can use synchronization primitives, such as event objects, to synchronize between the driver and the DPC. The driver can check the return code of <b>KeCancelTimer</b> to determine if the DPC is running. If so, the DPC can signal the event before exiting, and the driver can wait for that event to be reset to the not-signaled state.

Since for periodic timers <b>KeCancelTimer</b> always returns <b>TRUE</b>, drivers must use a different technique to wait until the DPC has completed. Use the <a href="..\wdm\nf-wdm-keflushqueueddpcs.md">KeFlushQueuedDpcs</a> routine to block until the DPC executes.

Drivers do not need to synchronize for data stored in global variables or driver object extensions. The system automatically calls <b>KeFlushQueuedDpcs</b> before deallocating either of these regions.

For more information about timer objects, see <a href="https://msdn.microsoft.com/b58487de-6e9e-45f4-acb8-9233c8718ee2">Timer Objects and DPCs</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | IrqlKeDispatchLte, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-kesettimer.md">KeSetTimer</a>

<a href="..\wdm\nf-wdm-kereadstatetimer.md">KeReadStateTimer</a>

<a href="..\wdm\nf-wdm-keinitializetimer.md">KeInitializeTimer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeCancelTimer routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>