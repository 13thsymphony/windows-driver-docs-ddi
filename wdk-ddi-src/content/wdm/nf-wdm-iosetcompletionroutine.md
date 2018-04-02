---
UID: NF:wdm.IoSetCompletionRoutine
title: IoSetCompletionRoutine function
author: windows-driver-content
description: The IoSetCompletionRoutine routine registers an IoCompletion routine, which will be called when the next-lower-level driver has completed the requested operation for the given IRP.
old-location: kernel\iosetcompletionroutine.htm
old-project: kernel
ms.assetid: 09c645d0-4d46-46c0-9256-8d2ddd3670b9
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoSetCompletionRoutine, IoSetCompletionRoutine routine [Kernel-Mode Driver Architecture], k104_cbc51352-796e-4b64-9725-7d8a08c4aea9.xml, kernel.iosetcompletionroutine, wdm/IoSetCompletionRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CompleteRequest, CompleteRequestStatusCheck, CompletionRoutineRegistered, IoAllocateForward, IoAllocateIrpSignalEventInCompletion, IoAllocateIrpSignalEventInCompletion2, IoAllocateIrpSignalEventInCompletion3, IoAllocateIrpSignalEventInCompletionTimeout, IoBuildFsdForward, IoBuildFsdIrpSignalEventInCompletion, IoBuildFsdIrpSignalEventInCompletion2, IoBuildFsdIrpSignalEventInCompletion3, IoBuildFsdIrpSignalEventInCompletionTimeout, IoSetCompletionRoutineNonPnpDriver, LowerDriverReturn, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PendedCompletedRequest, SignalEventInCompletion, SignalEventInCompletion2, SignalEventInCompletion3, StartDeviceWait, StartDeviceWait3, SetCompletionRoutineFromDispatch, IoFreeIrp
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	IoSetCompletionRoutine
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoSetCompletionRoutine function
The <b>IoSetCompletionRoutine</b> routine registers an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine, which will be called when the next-lower-level driver has completed the requested operation for the given IRP.

## Syntax

```
void IoSetCompletionRoutine(
  PIRP                   Irp,
  PIO_COMPLETION_ROUTINE CompletionRoutine,
  __drv_aliasesMem PVOID Context,
  BOOLEAN                InvokeOnSuccess,
  BOOLEAN                InvokeOnError,
  BOOLEAN                InvokeOnCancel
);
```

## Parameters

`Irp`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> that the driver is processing.

`CompletionRoutine`

Specifies the entry point for the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine, which is called when the next-lower driver completes the packet.

`Context`

Pointer to a driver-determined context to pass to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine. Context information must be stored in nonpaged memory, because the <i>IoCompletion</i> routine is called at IRQL &lt;= DISPATCH_LEVEL.

`InvokeOnSuccess`

Specifies whether the completion routine is called if the IRP is completed with a success status value in the IRP's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure, based on results of the <b>NT_SUCCESS</b> macro (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS values</a>).

`InvokeOnError`

Specifies whether the completion routine is called if the IRP is completed with a nonsuccess status value in the IRP's <b>IO_STATUS_BLOCK</b> structure.

`InvokeOnCancel`

Specifies whether the completion routine is called if a driver or the kernel has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548338">IoCancelIrp</a> to cancel the IRP.


## Return Value

None

## Remarks

<div class="alert"><b>Note</b>    Only a driver that can guarantee it will not be unloaded before its completion routine finishes can use <b>IoSetCompletionRoutine</b>. Otherwise, the driver must use <a href="https://msdn.microsoft.com/library/windows/hardware/ff549686">IoSetCompletionRoutineEx</a>, which prevents the driver from unloading until its completion routine executes.</div>
<div> </div>
This routine sets the transfer address of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine in the given IRP. The lowest-level driver in a chain of layered drivers cannot call this routine.

<b>IoSetCompletionRoutine</b> registers the specified routine to be called when the next-lower-level driver has completed the requested operation in any or all of the following ways:

<ul>
<li>
With a success status value

</li>
<li>
With a nonsuccess status value

</li>
<li>
By canceling the IRP

</li>
</ul>
Usually, the I/O status block is set by the underlying device driver. It is read but not altered by any higher-level drivers' <i>IoCompletion</i> routines.

Higher-level drivers that allocate IRP's with <a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a> must call this routine with all <i>InvokeOn</i>Xxx parameters set to <b>TRUE</b> before passing the driver-allocated IRP to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>. When the <i>IoCompletion</i> routine is called with such an IRP, it must free the driver-allocated IRP and any other resources that the driver set up for the request, such as MDLs with <a href="https://msdn.microsoft.com/library/windows/hardware/ff548324">IoBuildPartialMdl</a>. Such a driver should return STATUS_MORE_PROCESSING_REQUIRED when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a> to forestall the I/O manager's completion processing for the driver-allocated IRP.

Non-PnP drivers that might be unloaded before their <i>IoCompletion</i> routines run should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff549686">IoSetCompletionRoutineEx</a> instead.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | CompleteRequest, CompleteRequestStatusCheck, CompletionRoutineRegistered, IoAllocateForward, IoAllocateIrpSignalEventInCompletion, IoAllocateIrpSignalEventInCompletion2, IoAllocateIrpSignalEventInCompletion3, IoAllocateIrpSignalEventInCompletionTimeout, IoBuildFsdForward, IoBuildFsdIrpSignalEventInCompletion, IoBuildFsdIrpSignalEventInCompletion2, IoBuildFsdIrpSignalEventInCompletion3, IoBuildFsdIrpSignalEventInCompletionTimeout, IoSetCompletionRoutineNonPnpDriver, LowerDriverReturn, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PendedCompletedRequest, SignalEventInCompletion, SignalEventInCompletion2, SignalEventInCompletion3, StartDeviceWait, StartDeviceWait3, SetCompletionRoutineFromDispatch, IoFreeIrp |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548324">IoBuildPartialMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549686">IoSetCompletionRoutineEx</a>