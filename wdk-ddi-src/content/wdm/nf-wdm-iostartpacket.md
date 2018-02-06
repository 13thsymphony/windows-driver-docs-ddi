---
UID: NF:wdm.IoStartPacket
title: IoStartPacket function
author: windows-driver-content
description: The IoStartPacket routine calls the driver's StartIo routine with the given IRP or inserts the IRP into the device queue associated with the given device object if the device is already busy.
old-location: kernel\iostartpacket.htm
old-project: kernel
ms.assetid: b1fa148e-73e2-437f-bd3a-e879bd457c76
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/IoStartPacket, IoStartPacket routine [Kernel-Mode Driver Architecture], IoStartPacket, kernel.iostartpacket, k104_d27461b9-32fe-4d7b-853d-fd110fcdb644.xml
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoStartPacket
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoStartPacket function
The <b>IoStartPacket</b> routine calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine with the given IRP or inserts the IRP into the device queue associated with the given device object if the device is already busy.

## Syntax

````
VOID IoStartPacket(
  _In_     PDEVICE_OBJECT DeviceObject,
  _In_     PIRP           Irp,
  _In_opt_ PULONG         Key,
  _In_opt_ PDRIVER_CANCEL CancelFunction
);
````

## Parameters

`DeviceObject`

Pointer to the target device object for the IRP.

`Irp`

Pointer to the IRP to be processed.

`Key`

Pointer to a value that determines where to insert the packet into the device queue. If this is zero, the packet is inserted at the tail of the device queue.

`CancelFunction`

Specifies the entry point for a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/hh406716">Cancel</a> routine.


## Return Value

None

## Remarks

If the driver is already busy processing a request for the target device object, then the packet is queued in the device queue. Otherwise, this routine calls the driver's <i>StartIo</i> routine with the specified IRP.

If a non-NULL <i>CancelFunction</i> pointer is supplied, it is set in the IRP so the driver's <i>Cancel</i> routine is called if the IRP is canceled before its completion.

Drivers that do not have a <i>StartIo</i> routine cannot call <b>IoStartPacket</b>.

Callers of <b>IoStartPacket</b> must be running at IRQL &lt;= DISPATCH_LEVEL. Usually, this routine is called from a device driver's Dispatch routine at IRQL = PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL (see Remarks section)" |

## See Also

<a href="..\wdm\nf-wdm-iomarkirppending.md">IoMarkIrpPending</a>

<a href="..\wdm\nf-wdm-iosetcancelroutine.md">IoSetCancelRoutine</a>

<a href="..\ntifs\nf-ntifs-iostartnextpacket.md">IoStartNextPacket</a>

<a href="..\ntifs\nf-ntifs-iostartnextpacketbykey.md">IoStartNextPacketByKey</a>

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoStartPacket routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>