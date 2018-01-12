---
UID: NF:wdm.IoMarkIrpPending
title: IoMarkIrpPending function
author: windows-driver-content
description: The IoMarkIrpPending routine marks the specified IRP, indicating that a driver's dispatch routine subsequently returned STATUS_PENDING because further processing is required by other driver routines.
old-location: kernel\iomarkirppending.htm
old-project: kernel
ms.assetid: 424d5ebd-c871-40d8-b5b7-3a4a04fe60fa
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoMarkIrpPending
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
req.alt-api: IoMarkIrpPending
req.alt-loc: Wdm.h
req.ddi-compliance: CompleteRequestStatusCheck, CompletionEventChecking, IrpCancelField, LowerDriverReturn, MarkDevicePower, MarkingInterlockedQueuedIrps, MarkingQueuedIrps, MarkIrpPending, MarkIrpPending2, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PendedCompletedRequest3
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoMarkIrpPending function



## -description
The <b>IoMarkIrpPending</b> routine marks the specified IRP, indicating that a driver's dispatch routine subsequently returned STATUS_PENDING because further processing is required by other driver routines.



## -syntax

````
VOID IoMarkIrpPending(
  _Inout_ PIRP Irp
);
````


## -parameters

### -param Irp [in, out]

Pointer to the IRP to be marked as pending.


## -returns
None


## -remarks
Unless the driver's dispatch routine completes the IRP (by calling <a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>) or passes the IRP on to lower drivers, it must call <b>IoMarkIrpPending</b> with the IRP. Otherwise, the I/O manager attempts to complete the IRP as soon as the dispatch routine returns control.

After calling <b>IoMarkIrpPending</b>, the dispatch routine must return STATUS_PENDING, even if some routine completes the IRP (by calling <a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>) before the dispatch routine that called <b>IoMarkIrpPending</b> returns.

If a driver queues incoming IRPs, it should call <b>IoMarkIrpPending</b> before it queues each IRP. Otherwise, an IRP could be dequeued, completed by another driver routine, and freed by the system before the call to <b>IoMarkIrpPending</b> occurs, thereby causing a crash.

If a driver sets an <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine for an IRP and then passes the IRP down to a lower driver, the <i>IoCompletion</i> routine should check the <b>IRP-&gt;PendingReturned</b> flag. If the flag is set, the <i>IoCompletion</i> routine must call <b>IoMarkIrpPending</b> with the IRP. (<i>IoCompletion</i> routines do not return STATUS_PENDING, however. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547084">Implementing an IoCompletion Routine</a>.) 

A driver that passes down the IRP and then waits on an event should not mark the IRP pending. Instead, its <i>IoCompletion</i> routine should signal the event and return STATUS_MORE_PROCESSING_REQUIRED.

If your driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a>, be careful not to modify the <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure in a way that could unintentionally affect the lower driver or the system's behavior with respect to that driver. In particular, your driver should not modify the <b>IO_STACK_LOCATION</b> structure's <b>Parameters</b> union, and should not call <b>IoMarkIrpPending</b>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975144">CompleteRequestStatusCheck</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975145">CompletionEventChecking</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547319">IrpCancelField</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548273">LowerDriverReturn</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975187">MarkDevicePower</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549015">MarkingInterlockedQueuedIrps</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549016">MarkingQueuedIrps</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549018">MarkIrpPending</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549021">MarkIrpPending2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975188">MarkPower</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975189">MarkPowerDown</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975190">MarkQueryRelations</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975191">MarkStartDevice</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975199">PendedCompletedRequest3</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iostartpacket.md">IoStartPacket</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoMarkIrpPending routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

