---
UID: NF:wdm.IoDeleteDevice
title: IoDeleteDevice function
author: windows-driver-content
description: The IoDeleteDevice routine removes a device object from the system, for example, when the underlying device is removed from the system.
old-location: kernel\iodeletedevice.htm
old-project: kernel
ms.assetid: 973549c3-c570-48ab-9a82-9398c920dbd9
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoDeleteDevice, IoDeleteDevice routine [Kernel-Mode Driver Architecture], k104_246c1fe6-75cc-434e-a1d4-7e573eff96de.xml, kernel.iodeletedevice, wdm/IoDeleteDevice
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
req.ddi-compliance: DeleteDevice, IrqlIoApcLte, PnpSurpriseRemove, RemoveLockCheck, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoDeleteDevice
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoDeleteDevice function
The <b>IoDeleteDevice</b> routine removes a device object from the system, for example, when the underlying device is removed from the system.

## Syntax

```
NTKERNELAPI VOID IoDeleteDevice(
  __drv_freesMem(Mem)PDEVICE_OBJECT DeviceObject
);
```

## Parameters

`DeviceObject`

Pointer to the device object to be deleted.


## Return Value

None

## Remarks

When handling a PnP <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> request, a PnP driver calls <b>IoDeleteDevice</b> to delete any associated device objects. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff546687">Handling an IRP_MN_REMOVE_DEVICE Request</a> for details.

A legacy driver should call this routine when it is being unloaded or when its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine encounters a fatal initialization error, such as being unable to properly initialize a physical device. This routine also is called when a driver reconfigures its devices dynamically. For example, a disk driver called to repartition a disk would call <b>IoDeleteDevice</b> to tear down the device objects representing partitions to be replaced.

A driver must release certain resources for which the driver supplied storage in its device extension before it calls <b>IoDeleteDevice</b>. For example, if the driver stores the pointer to its interrupt object(s) in the device extension, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549089">IoDisconnectInterrupt</a> before calling <b>IoDeleteDevice</b>.

A driver can call <b>IoDeleteDevice</b> only once for a given device object.

When a driver calls <b>IoDeleteDevice</b>, the I/O manager deletes the target device object if there are no outstanding references to it. However, if any outstanding references remain, the I/O manager marks the device object as "delete pending" and deletes the device object when the references are released.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |
| **DDI compliance rules** | DeleteDevice, IrqlIoApcLte, PnpSurpriseRemove, RemoveLockCheck, HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549089">IoDisconnectInterrupt</a>