---
UID: NF:wdm.IoInvalidateDeviceState
title: IoInvalidateDeviceState function
author: windows-driver-content
description: The IoInvalidateDeviceState routine notifies the PnP manager that some aspect of the PnP state of a device has changed.
old-location: kernel\ioinvalidatedevicestate.htm
old-project: kernel
ms.assetid: ca27e8d3-80ee-467c-9c88-19770cd86d94
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoInvalidateDeviceState, IoInvalidateDeviceState routine [Kernel-Mode Driver Architecture], k104_05ef79e6-a7d1-4de4-aefa-5aa7d9121f04.xml, kernel.ioinvalidatedevicestate, wdm/IoInvalidateDeviceState
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoInvalidateDeviceState
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoInvalidateDeviceState function
The <b>IoInvalidateDeviceState</b> routine notifies the PnP manager that some aspect of the PnP state of a device has changed.

## Syntax

```
NTKERNELAPI VOID IoInvalidateDeviceState(
  PDEVICE_OBJECT PhysicalDeviceObject
);
```

## Parameters

`PhysicalDeviceObject`

Pointer to the PDO for the device.


## Return Value

None

## Remarks

Drivers call this routine to indicate that something has changed with respect to one of the following aspects of a device's PnP state:

PNP_DEVICE_DISABLED

PNP_DEVICE_DONT_DISPLAY_IN_UI

PNP_DEVICE_FAILED

PNP_DEVICE_NOT_DISABLEABLE

PNP_DEVICE_REMOVED

PNP_DEVICE_RESOURCE_REQUIREMENTS_CHANGED

For descriptions of the preceding constants, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559618">PNP_DEVICE_STATE</a>.

In response to this routine, the PnP manager sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551698">IRP_MN_QUERY_PNP_DEVICE_STATE</a> request to the device stack, to determine the current PnP state of the device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551698">IRP_MN_QUERY_PNP_DEVICE_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559618">PNP_DEVICE_STATE</a>