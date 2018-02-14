---
UID: NF:ntddk.IoAllocateController
title: IoAllocateController function
author: windows-driver-content
description: The IoAllocateController routine sets up the call to a driver-supplied ControllerControl routine as soon as the device controller, represented by the given controller object, is available to carry out an I/O operation for the target device, represented by the given device object.
old-location: kernel\ioallocatecontroller.htm
old-project: kernel
ms.assetid: bfeec8b1-48fb-420e-b602-699a5f2d659a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/IoAllocateController, kernel.ioallocatecontroller, k104_b550c6ff-9d5c-4497-98bb-6781b4e6abd8.xml, IoAllocateController, IoAllocateController routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch, HwStorPortProhibitedDDIs, IrqlDispatch(storport), SpNoWait, StorPortStartIo
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoAllocateController
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# IoAllocateController function
The <b>IoAllocateController</b> routine sets up the call to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff542049">ControllerControl</a> routine as soon as the device controller, represented by the given controller object, is available to carry out an I/O operation for the target device, represented by the given device object.

## Syntax

````
VOID IoAllocateController(
  _In_     PCONTROLLER_OBJECT ControllerObject,
  _In_     PDEVICE_OBJECT     DeviceObject,
  _In_     PDRIVER_CONTROL    ExecutionRoutine,
  _In_opt_ PVOID              Context
);
````

## Parameters

`ControllerObject`

Pointer to a driver-created controller object, usually representing a physical controller to be allocated for an I/O operation on an attached device.

`DeviceObject`

Pointer to the device object, representing the target device of the current IRP.

`ExecutionRoutine`

Pointer to the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff542049">ControllerControl</a> routine.

`Context`

Pointer to a driver-determined context, passed to the driver's <i>ControllerControl</i> routine when it is called.


## Return Value

None

## Remarks

This routine reserves exclusive access to the hardware controller for the specified device.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff542049">ControllerControl</a> routine returns a value indicating whether the controller remains allocated to the device, either <b>DeallocateObject</b> or <b>KeepObject</b>. If it returns <b>KeepObject</b>, the driver must subsequently call <b>IoFreeController</b> to release the controller object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** | IrqlDispatch, HwStorPortProhibitedDDIs, IrqlDispatch(storport), SpNoWait, StorPortStartIo |

## See Also

<a href="..\ntddk\nf-ntddk-iofreecontroller.md">IoFreeController</a>



<a href="..\ntddk\nf-ntddk-iocreatecontroller.md">IoCreateController</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542049">ControllerControl</a>



<a href="..\ntddk\nf-ntddk-iodeletecontroller.md">IoDeleteController</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoAllocateController routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>