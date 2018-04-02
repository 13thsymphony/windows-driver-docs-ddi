---
UID: NF:wdm.IoInvalidateDeviceRelations
title: IoInvalidateDeviceRelations function
author: windows-driver-content
description: The IoInvalidateDeviceRelations routine notifies the PnP manager that the relations for a device (such as bus relations, ejection relations, removal relations, and the target device relation) have changed.
old-location: kernel\ioinvalidatedevicerelations.htm
old-project: kernel
ms.assetid: f312afec-10b3-4049-a4c1-154c11b4a869
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoInvalidateDeviceRelations, IoInvalidateDeviceRelations routine [Kernel-Mode Driver Architecture], k104_c839e20b-2be6-4586-86c9-57c773bf755f.xml, kernel.ioinvalidatedevicerelations, wdm/IoInvalidateDeviceRelations
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
req.ddi-compliance: HwStorPortProhibitedDDIs
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
-	IoInvalidateDeviceRelations
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoInvalidateDeviceRelations function
The <b>IoInvalidateDeviceRelations</b> routine notifies the PnP manager that the relations for a device (such as bus relations, ejection relations, removal relations, and the target device relation) have changed.

## Syntax

```
NTKERNELAPI VOID IoInvalidateDeviceRelations(
  PDEVICE_OBJECT       DeviceObject,
  DEVICE_RELATION_TYPE Type
);
```

## Parameters

`DeviceObject`

Pointer to the PDO for the device.

`Type`

Specifies a <b>DEVICE_RELATION_TYPE</b> enumeration value that describes the type of relations that have changed. Possible values include <b>BusRelations</b>, <b>EjectionRelations</b>, <b>RemovalRelations</b>, and <b>TargetDeviceRelation</b>. Starting with Windows 7, the <b>PowerRelations</b> value is also supported.


## Return Value

None

## Remarks

For some relation types, such as <b>BusRelations</b>, this routine causes the PnP manager or power manager to gather updated relations information by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a> request to the drivers for the device. For other relation types, such as <b>EjectionRelations</b>, the PnP manager does not need to gather new relation information immediately; the PnP manager queries drivers for ejection relations only when it is preparing to eject a device.

After a bus driver calls <b>IoInvalidateDeviceRelations</b> to inform the PnP manager that a device has disappeared, the bus driver must continue to handle PnP IRPs for that device until it receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> request. In response to this IRP, the bus driver returns STATUS_NO_SUCH_DEVICE. Until the bus driver successfully completes the <b>IRP_MN_REMOVE_DEVICE</b> request, the bus driver can access the device extension to check its flags for the device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>