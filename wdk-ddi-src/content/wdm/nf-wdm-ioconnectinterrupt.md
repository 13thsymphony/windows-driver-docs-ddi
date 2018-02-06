---
UID: NF:wdm.IoConnectInterrupt
title: IoConnectInterrupt function
author: windows-driver-content
description: The IoConnectInterrupt routine registers a device driver's InterruptService routine (ISR), so that it will be called when a device interrupts on any of a specified set of processors.
old-location: kernel\ioconnectinterrupt.htm
old-project: kernel
ms.assetid: a0f9a339-f548-47a2-92ab-ccd341592384
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoConnectInterrupt routine [Kernel-Mode Driver Architecture], k104_efa094e0-ac29-491b-803a-8470ed39c915.xml, kernel.ioconnectinterrupt, IoConnectInterrupt, wdm/IoConnectInterrupt
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
req.ddi-compliance: IrqlIoPassive2, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoConnectInterrupt
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoConnectInterrupt function
The <b>IoConnectInterrupt</b> routine registers a device driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine (ISR), so that it will be called when a device interrupts on any of a specified set of processors.

## Syntax

````
NTSTATUS IoConnectInterrupt(
  _Out_    PKINTERRUPT       *InterruptObject,
  _In_     PKSERVICE_ROUTINE ServiceRoutine,
  _In_opt_ PVOID             ServiceContext,
  _In_opt_ PKSPIN_LOCK       SpinLock,
  _In_     ULONG             Vector,
  _In_     KIRQL             Irql,
  _In_     KIRQL             SynchronizeIrql,
  _In_     KINTERRUPT_MODE   InterruptMode,
  _In_     BOOLEAN           ShareVector,
  _In_     KAFFINITY         ProcessorEnableMask,
  _In_     BOOLEAN           FloatingSave
);
````

## Parameters

`InterruptObject`

Pointer to the address of driver-supplied storage for a pointer to a set of interrupt objects. This pointer must be passed in subsequent calls to <a href="..\wdm\nf-wdm-kesynchronizeexecution.md">KeSynchronizeExecution</a>.

`ServiceRoutine`

Pointer to the entry point for the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine.

`ServiceContext`

Pointer to the driver-determined context that will be supplied to the <i>InterruptService</i> routine when it is called. The <i>ServiceContext</i> area must be in resident memory: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the device driver. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff559930">Providing ISR Context Information</a> for details.

`SpinLock`

Pointer to an initialized spin lock, for which the driver supplies the storage, that will be used to synchronize access to driver-determined data shared by other driver routines. This parameter is required if the ISR handles more than one vector or if the driver has more than one ISR. Otherwise, the driver need not allocate storage for an interrupt spin lock and the input pointer is <b>NULL</b>.

`Vector`

Specifies the interrupt vector passed in the interrupt resource at the <b>u.Interrupt.Vector</b> member of <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>.

`Irql`

Specifies the DIRQL passed in the interrupt resource at the <b>u.Interrupt.Level</b> member of <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b>.

`SynchronizeIrql`

Specifies the DIRQL at which the ISR will run. If the ISR handles more than one interrupt vector or the driver has more than one ISR, this value must be the highest of the <i>Irql</i> values passed at <b>u.Interrupt.Level</b> in each interrupt resource. Otherwise, the <i>Irql</i> and <i>SynchronizeIrql</i> values are identical.

`InterruptMode`

Specifies whether the device interrupt is <b>LevelSensitive</b> or <b>Latched</b>.

`ShareVector`

Specifies whether the interrupt vector is sharable.

`ProcessorEnableMask`

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a> value representing the set of processors on which device interrupts can occur in this platform. This value is passed in the interrupt resource at <b>u.Interrupt.Affinity</b>.

`FloatingSave`

Specifies whether to save the floating-point stack when the driver's device interrupts. For x86-based and Itanium-based platforms, this value must be set to <b>FALSE</b>. For more information about saving floating-point and MMX state, see <a href="https://msdn.microsoft.com/73414084-4054-466a-b64c-5c81b224be92">Using Floating Point or MMX in a WDM Driver</a>.


## Return Value

<b>IoConnectInterrupt</b> can return one of the following NTSTATUS values:

## Remarks

New drivers should use the <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> routine, which is easier to use. Drivers for devices that support message-signaled interrupts (MSI) must use <b>IoConnectInterruptEx</b>.

A PnP driver should call <b>IoConnectInterrupt</b> as part of device start-up, before it completes the PnP <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request.

When a driver receives an <b>IRP_MN_START_DEVICE</b> request, the driver receives raw and translated hardware resources in the <b>Parameters.StartDevice.AllocatedResources</b> and  <b>Parameters.StartDevice.AllocatedResourcesTranslated</b> members of the IRP's <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure, respectively. To connect its interrupt, the driver uses the resources at <b>AllocatedResourcesTranslated.List.PartialResourceList.PartialDescriptors[]</b>. The driver must scan the array of partial descriptors for resources of type <b>CmResourceTypeInterrupt</b>.

If the driver supplies the storage for the <i>SpinLock</i>, it must call <a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a> before passing its interrupt spin lock to <b>IoConnectInterrupt</b>.

On return from a successful call to <b>IoConnectInterrupt</b>, the caller's ISR can be called if interrupts are enabled on the driver's device or if <i>ShareVector</i> was set to <b>TRUE</b>. Drivers must not enable interrupts until after <b>IoConnectInterrupt</b> returns.

The KAFFINITY type is an affinity mask that represents a set of logical processors in a group. The KAFFINITY type is 32 bits on a 32-bit version of Windows and is 64 bits on a 64-bit version of Windows.

If a group contains <i>n</i> logical processors, the processors are numbered from 0 to <i>n</i>-1. Processor number <i>i</i> in the group is represented by bit <i>i</i> in the affinity mask, where <i>i</i> is in the range 0 to <i>n</i>-1. Affinity mask bits that do not correspond to logical processors are always zero.

For example, if a KAFFINITY value identifies the active processors in a group, the mask bit for a processor is one if the processor is active, and is zero if the processor is not active.

The number of bits in the affinity mask determines the maximum number of logical processors in a group. For a 64-bit version of Windows, the maximum number of processors per group is 64. For a 32-bit version of Windows, the maximum number of processors per group is 32. Call the <a href="..\wdm\nf-wdm-kequerymaximumprocessorcountex.md">KeQueryMaximumProcessorCountEx</a> routine to obtain the maximum number of processors per group. This number depends on the hardware configuration of the multiprocessor system, but can never exceed the fixed 64-processor and 32-processor limits that are set by the 64-bit and 32-bit versions of Windows, respectively.

The <a href="..\miniport\ns-miniport-_group_affinity.md">GROUP_AFFINITY</a> structure contains an affinity mask and a group number. The group number identifies the group to which the affinity mask applies.

Kernel routines that use the KAFFINITY type include <b>IoConnectInterrupt</b>, <a href="..\wdm\nf-wdm-kequeryactiveprocessorcount.md">KeQueryActiveProcessorCount</a>, and <a href="..\wdm\nf-wdm-kequeryactiveprocessors.md">KeQueryActiveProcessors</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlIoPassive2, PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-iodisconnectinterrupt.md">IoDisconnectInterrupt</a>

<a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>

<a href="..\wdm\nf-wdm-kesynchronizeexecution.md">KeSynchronizeExecution</a>

<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>

<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoConnectInterrupt routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>