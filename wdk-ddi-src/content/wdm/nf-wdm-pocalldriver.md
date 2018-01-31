---
UID : NF:wdm.PoCallDriver
title : PoCallDriver function
author : windows-driver-content
description : The PoCallDriver routine passes a power IRP to the next-lower driver in the device stack. (Windows Server 2003, Windows XP, and Windows 2000 only.).
old-location : kernel\pocalldriver.htm
old-project : kernel
ms.assetid : e5ce7786-717a-4e0f-bc57-342655a59ca1
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PoCallDriver, wdm/PoCallDriver, PoCallDriver routine [Kernel-Mode Driver Architecture], kernel.pocalldriver, portn_2045d7d3-993d-49e6-aaf5-52d3c1316382.xml
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
req.ddi-compliance : CompleteRequestStatusCheck, CompletionRoutineRegistered, DeleteDevice, ForwardedAtBadIrql, ForwardedAtBadIrqlAllocate, ForwardedAtBadIrqlFsdAsync, ForwardedAtBadIrqlFsdSync, IoAllocateForward, IoAllocateIrpSignalEventInCompletionTimeout, IoBuildDeviceControlWait, IoBuildDeviceControlWaitTimeout, IoBuildFsdForward, IoBuildSynchronousFsdRequestWait, IoBuildSynchronousFsdRequestWaitTimeout, IoSetCompletionRoutineExCheck, IrpProcessingComplete, LowerDriverReturn, MarkDevicePower, MarkingQueuedIrps, MarkIrpPending, MarkIrpPending2, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PendedCompletedRequest, PendedCompletedRequest2, PendedCompletedRequest3, PendedCompletedRequestEx, PnpIrpCompletion, PowerDownFail, PowerUpFail, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockMnRemove2, RemoveLockMnSurpriseRemove, RemoveLockQueryMnRemove, TargetRelationNeedsRef, WmiForward, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : See Remarks section.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# PoCallDriver function
The <b>PoCallDriver</b> routine passes a power <a href="..\wdm\ns-wdm-_irp.md">IRP</a> to the next-lower driver in the device stack. (Windows Server 2003, Windows XP, and Windows 2000 only.)

## Syntax

````
NTSTATUS PoCallDriver(
  _In_    PDEVICE_OBJECT DeviceObject,
  _Inout_ PIRP           Irp
);
````

## Parameters

`DeviceObject`

A pointer to the driver-created <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> to which the IRP is to be routed.

`Irp`

A pointer to an IRP.


## Return Value

<b>PoCallDriver</b> returns STATUS_SUCCESS to indicate success. It returns STATUS_PENDING if it has queued the IRP.

## Remarks

Beginning with Windows Vista, drivers should call <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>, not <b>PoCallDriver</b> to pass a power IRP to the next-lower driver. However, on Windows Server 2003, Windows XP, and Windows 2000, drivers must call <b>PoCallDriver</b>, not <b>IoCallDriver</b>  to pass a power IRP to the next-lower driver. On Windows Server 2003, Windows XP, an Windows 2000, drivers must also call <a href="..\ntifs\nf-ntifs-postartnextpowerirp.md">PoStartNextPowerIrp</a> before calling <b>PoCallDriver</b>.

A driver that requires a new IRP should call <a href="..\wdm\nf-wdm-porequestpowerirp.md">PoRequestPowerIrp</a>. A driver must not allocate its own power IRP.

When passing a power IRP down to the next-lower driver, the caller should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a> or <a href="..\wdm\nf-wdm-iocopycurrentirpstacklocationtonext.md">IoCopyCurrentIrpStackLocationToNext</a> to set the IRP stack location, then call <b>PoCallDriver</b>. Use <b>IoCopyCurrentIrpStackLocationToNext</b> if processing the IRP requires setting an <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine, or <b>IoSkipCurrentStackLocation</b> if no <i>IoCompletion</i> routine is required.

When a device is powering up, its drivers must set <i>IoCompletion</i> routines to perform start-up tasks (initializing the device, restoring context, and so on) after the bus driver has set the device in the working state. Set <i>IoCompletion</i> routines before calling <b>PoCallDriver</b>.

When a device is powering down, its drivers must perform necessary power-down tasks before passing the IRP to the next lower driver. After the IRP has reached the bus driver, the device will be powered off and its drivers will no longer have access to it. On Windows Server 2003, Windows XP, and Windows 2000, an <i>IoCompletion</i> routine that is associated with a power-down IRP is only required to call <b>PoStartNextPowerIrp</b>.

Only one inrush IRP can be active in the system at a time. When passing a power-up IRP for a device that requires inrush current (in other words, the DO_POWER_INRUSH flag is set in the device object), <b>PoCallDriver</b> checks whether another inrush IRP is already active. If so, <b>PoCallDriver</b> queues the current IRP for handling after the previous IRP completes, and then returns STATUS_PENDING. For more information about inrush IRPs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563746">Setting Device Object Flags for Power Management</a>. 

If an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a> request is already active for <i>DeviceObject</i>, <b>PoCallDriver</b> queues this IRP and returns STATUS_PENDING.

On Windows 2000 and later systems, pageable drivers (the DO_POWER_PAGABLE flag is set in the device object) must call <b>PoCallDriver</b> at IRQL = PASSIVE_LEVEL. Drivers that cannot be paged (DO_POWER_PAGABLE is not set in the device object) or that require inrush current (DO_POWER_INRUSH is set in the device object) can call <b>PoCallDriver</b> at IRQL = PASSIVE_LEVEL or DISPATCH_LEVEL.

On Windows 98/Me, all drivers call <b>PoCallDriver</b> at IRQL = PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | See Remarks section. |
| **DDI compliance rules** | CompleteRequestStatusCheck, CompletionRoutineRegistered, DeleteDevice, ForwardedAtBadIrql, ForwardedAtBadIrqlAllocate, ForwardedAtBadIrqlFsdAsync, ForwardedAtBadIrqlFsdSync, IoAllocateForward, IoAllocateIrpSignalEventInCompletionTimeout, IoBuildDeviceControlWait, IoBuildDeviceControlWaitTimeout, IoBuildFsdForward, IoBuildSynchronousFsdRequestWait, IoBuildSynchronousFsdRequestWaitTimeout, IoSetCompletionRoutineExCheck, IrpProcessingComplete, LowerDriverReturn, MarkDevicePower, MarkingQueuedIrps, MarkIrpPending, MarkIrpPending2, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PendedCompletedRequest, PendedCompletedRequest2, PendedCompletedRequest3, PendedCompletedRequestEx, PnpIrpCompletion, PowerDownFail, PowerUpFail, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockMnRemove2, RemoveLockMnSurpriseRemove, RemoveLockQueryMnRemove, TargetRelationNeedsRef, WmiForward, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a>

<a href="..\wdm\nf-wdm-porequestpowerirp.md">PoRequestPowerIrp</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>

<a href="..\wdm\nf-wdm-iocopycurrentirpstacklocationtonext.md">IoCopyCurrentIrpStackLocationToNext</a>

<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a>

<a href="..\ntifs\nf-ntifs-postartnextpowerirp.md">PoStartNextPowerIrp</a>

<a href="..\wdm\ns-wdm-_irp.md">IRP</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoCallDriver routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>