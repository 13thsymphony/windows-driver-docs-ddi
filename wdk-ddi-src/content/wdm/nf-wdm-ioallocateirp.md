---
UID: NF:wdm.IoAllocateIrp
title: IoAllocateIrp function
author: windows-driver-content
description: The IoAllocateIrp routine allocates an IRP, given the number of I/O stack locations for each driver layered under the caller, and, optionally, for the caller.
old-location: kernel\ioallocateirp.htm
old-project: kernel
ms.assetid: 40abbdf8-3712-4724-8aef-16c247780c86
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoAllocateIrp, IoAllocateIrp routine [Kernel-Mode Driver Architecture], k104_326eb80d-9bc3-4a91-9f33-710f7975808a.xml, kernel.ioallocateirp, wdm/IoAllocateIrp
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
req.ddi-compliance: ForwardedAtBadIrqlAllocate, IoAllocateComplete, IoAllocateForward, IoAllocateFree, IoAllocateIrpSignalEventInCompletion, IoAllocateIrpSignalEventInCompletion2, IoAllocateIrpSignalEventInCompletion3, IoAllocateIrpSignalEventInCompletionTimeout, IoReuseIrp, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, HwStorPortProhibitedDDIs, IoFreeIrp, SpNoWait, StorPortStartIo
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoAllocateIrp
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoAllocateIrp function
The <b>IoAllocateIrp</b> routine allocates an IRP, given the number of I/O stack locations for each driver layered under the caller, and, optionally, for the caller.

## Syntax

````
PIRP IoAllocateIrp(
  _In_ CCHAR   StackSize,
  _In_ BOOLEAN ChargeQuota
);
````

## Parameters

`StackSize`

Specifies the number of I/O stack locations to be allocated for the IRP. This value must be at least equal to the <b>StackSize</b> of the next-lower driver's device object, but can be one greater than this value. The calling driver need not allocate a stack location in the IRP for itself.

`ChargeQuota`

Setting this to <b>TRUE</b> causes the memory allocated for the IRP to be charged against the quota for the current process. Should be set to <b>FALSE</b> by intermediate drivers. This can be set to <b>TRUE</b> only by highest-level drivers that are called in the context of the thread that originates the I/O request for which the driver is allocating another IRP.


## Return Value

<b>IoAllocateIrp</b> returns a pointer to an IRP, which was allocated from nonpaged system space, or <b>NULL</b> if an IRP could not be allocated.

## Remarks

The <b>IoAllocateIrp</b> routine does not associate the IRP with a thread. The allocating driver must free the IRP instead of completing it back to the I/O manager.

An intermediate or highest-level driver can call <b>IoAllocateIrp</b> to create IRPs for requests it sends to lower-level drivers. Such a driver must initialize the IRP and must set its <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine in the IRP it creates so the caller can dispose of the IRP when lower-level drivers have completed processing of the request.

<b>IoAllocateIrp</b> automatically initializes the IRP's members. Do not use <b>IoInitializeIrp</b> to initialize the IRP before its first use. (You can use <b>IoInitializeIrp</b> to reuse an IRP that you have already used under certain special circumstances. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561107">Reusing IRPs</a> for details.)

An intermediate or highest-level driver also can call <a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a>, <a href="..\wdm\nf-wdm-iobuildasynchronousfsdrequest.md">IoBuildAsynchronousFsdRequest</a> or <a href="..\wdm\nf-wdm-iobuildsynchronousfsdrequest.md">IoBuildSynchronousFsdRequest</a> to set up requests it sends to lower-level drivers. Only a highest-level driver can call <a href="..\ntddk\nf-ntddk-iomakeassociatedirp.md">IoMakeAssociatedIrp</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | ForwardedAtBadIrqlAllocate, IoAllocateComplete, IoAllocateForward, IoAllocateFree, IoAllocateIrpSignalEventInCompletion, IoAllocateIrpSignalEventInCompletion2, IoAllocateIrpSignalEventInCompletion3, IoAllocateIrpSignalEventInCompletionTimeout, IoReuseIrp, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, HwStorPortProhibitedDDIs, IoFreeIrp, SpNoWait, StorPortStartIo |

## See Also

<a href="..\ntddk\nf-ntddk-iomakeassociatedirp.md">IoMakeAssociatedIrp</a>



<a href="..\wdm\nf-wdm-iobuildsynchronousfsdrequest.md">IoBuildSynchronousFsdRequest</a>



<a href="..\wdm\ns-wdm-_irp.md">IRP</a>



<a href="..\wdm\nf-wdm-ioreuseirp.md">IoReuseIrp</a>



<a href="..\wdm\nf-wdm-iofreeirp.md">IoFreeIrp</a>



<a href="..\wdm\nf-wdm-iosetcompletionroutine.md">IoSetCompletionRoutine</a>



<a href="..\wdm\nf-wdm-iobuildasynchronousfsdrequest.md">IoBuildAsynchronousFsdRequest</a>



<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>



<a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoAllocateIrp routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>