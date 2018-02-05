---
UID : NC:wdm.DRIVER_CONTROL
title : DRIVER_CONTROL
author : windows-driver-content
description : This routine starts a DMA data-transfer or a data transfer operation.
old-location : kernel\adaptercontrol.htm
old-project : kernel
ms.assetid : b75b8937-793d-4d75-9bb7-2226096044f0
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.adaptercontrol, AdapterControl, ControllerControl, MyControl routine [Kernel-Mode Driver Architecture], MyControl, DRIVER_CONTROL, DRIVER_CONTROL, wdm/MyControl, DrvrRtns_1e3fb66d-8977-4894-a3ac-d310fdfa6515.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Called at DISPATCH_LEVEL.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product : Windows 10 or later.
---


# DRIVER_CONTROL function
This routine starts a DMA data-transfer or a data transfer operation.

## Syntax

```
DRIVER_CONTROL DriverControl;

_IRQL_requires_same_ IO_ALLOCATION_ACTION DriverControl(
  _DEVICE_OBJECT * DeviceObject,
  _IRP * Irp,
  PVOID MapRegisterBase,
  PVOID Context
)
{...}
```

## Parameters

`DeviceObject`

Caller-supplied pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure. This is the device object for the target device, previously created by the driver's <i>AddDevice</i> routine.

`Irp`

Caller-supplied pointer to an <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure. <i>Irp</i> is equal to the value of the <b>CurrentIrp</b> member of <i>DeviceObject</i> when the callback routine was registered.

`MapRegisterBase`

In the case of <i>AdapterControl</i>, this is a caller-supplied opaque value that represents  the map registers that the system has assigned for this transfer operation. The driver passes this value to <a href="..\wdm\nc-wdm-pflush_adapter_buffers.md">FlushAdapterBuffers</a>, <a href="..\wdm\nc-wdm-pfree_map_registers.md">FreeMapRegisters</a>, and <a href="..\wdm\nc-wdm-pmap_transfer.md">MapTransfer</a>.

In the case of <i>ControllerControl</i>, this is not used.

`Context`

Caller-supplied pointer to driver-defined context information, specified in a previous call to <a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>.


## Return Value

The routine must return one of the values defined by the <a href="..\wdm\ne-wdm-_io_allocation_action.md">IO_ALLOCATION_ACTION</a> enumeration. Drivers of bus-master devices return either <b>DeallocateObject</b> or <b>DeallocateObjectKeepRegisters</b>; drivers that use system DMA return <b>KeepObject</b>.

## Remarks

<b>About implementing <i>AdapterControl</i>:  </b><p class="note">To register an <i>AdapterControl</i> routine for a specific device object, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> to obtain an adapter object, then call <a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a> to request use of the adapter and to supply the <i>AdapterControl</i> routine's address. When the adapter is free, the system calls the <i>AdapterControl</i> routine.

<p class="note">If <i>AdapterControl</i> has been registered by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine, then the <i>Irp</i> parameter is guaranteed to point to the IRP currently being processed by the <i>StartIo</i> routine. Otherwise, drivers must set the <b>CurrentIrp</b> member of the device object structure before calling <b>AllocateAdapterChannel</b>.

<p class="note">For detailed information about implementing an <i>AdapterControl</i> routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566397">Writing AdapterControl Routines</a>.



<b>About implementing <i>ControllerControl</i>:  </b>A driver's <i>ControllerControl</i> routine executes in an arbitrary thread context at IRQL = DISPATCH_LEVEL.

To register a <i>ControllerControl</i> routine for a specific device object, a driver must call <a href="..\ntddk\nf-ntddk-iocreatecontroller.md">IoCreateController</a> to obtain a controller object, then call <a href="..\ntddk\nf-ntddk-ioallocatecontroller.md">IoAllocateController</a> to request use of the controller and to supply the <i>ControllerControl</i> routine's address. When the controller is free, the system calls the <i>ControllerControl</i> routine.

For detailed information about implementing a <i>ControllerControl</i> routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566405">Writing ControllerControl Routines</a>. Also see <a href="https://msdn.microsoft.com/74b6685a-018f-4cb1-9332-424631aad85c">Controller Objects</a>.



The DRIVER_CONTROL function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the DRIVER_CONTROL function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | Called at DISPATCH_LEVEL. |

## See Also

<a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DRIVER_CONTROL routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>