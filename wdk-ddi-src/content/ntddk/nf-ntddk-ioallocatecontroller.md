---
UID: NF:ntddk.IoAllocateController
title: IoAllocateController function
author: windows-driver-content
description: The IoAllocateController routine sets up the call to a driver-supplied ControllerControl routine as soon as the device controller, represented by the given controller object, is available to carry out an I/O operation for the target device, represented by the given device object.
old-location: kernel\ioallocatecontroller.htm
old-project: kernel
ms.assetid: bfeec8b1-48fb-420e-b602-699a5f2d659a
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoAllocateController, IoAllocateController routine [Kernel-Mode Driver Architecture], k104_b550c6ff-9d5c-4497-98bb-6781b4e6abd8.xml, kernel.ioallocatecontroller, ntddk/IoAllocateController
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoAllocateController
product:
- Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# IoAllocateController function
The <b>IoAllocateController</b> routine sets up the call to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff542049">ControllerControl</a> routine as soon as the device controller, represented by the given controller object, is available to carry out an I/O operation for the target device, represented by the given device object.

## Syntax

```
NTKERNELAPI VOID IoAllocateController(
  PCONTROLLER_OBJECT ControllerObject,
  PDEVICE_OBJECT     DeviceObject,
  PDRIVER_CONTROL    ExecutionRoutine,
  PVOID              Context
);
```

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
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** | IrqlDispatch, HwStorPortProhibitedDDIs, IrqlDispatch(storport), SpNoWait, StorPortStartIo |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542049">ControllerControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548395">IoCreateController</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549078">IoDeleteController</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549104">IoFreeController</a>