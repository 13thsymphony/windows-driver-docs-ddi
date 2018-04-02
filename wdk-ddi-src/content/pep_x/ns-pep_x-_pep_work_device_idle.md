---
UID: NS:pep_x._PEP_WORK_DEVICE_IDLE
title: "_PEP_WORK_DEVICE_IDLE"
author: windows-driver-content
description: The PEP_WORK_DEVICE_IDLE structure indicates whether to ignore the idle time-out for the specified device.
old-location: kernel\pep_work_device_idle.htm
old-project: kernel
ms.assetid: 054D45D8-EDAA-41F2-9884-4301F08B67CB
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_WORK_DEVICE_IDLE, PEP_WORK_DEVICE_IDLE, PEP_WORK_DEVICE_IDLE structure [Kernel-Mode Driver Architecture], PPEP_WORK_DEVICE_IDLE, PPEP_WORK_DEVICE_IDLE structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_DEVICE_IDLE, kernel.pep_work_device_idle, pep_x/PEP_WORK_DEVICE_IDLE, pep_x/PPEP_WORK_DEVICE_IDLE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pepfx.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pep_x.h
api_name:
-	PEP_WORK_DEVICE_IDLE
product: Windows
targetos: Windows
req.typenames: PEP_WORK_DEVICE_IDLE, *PPEP_WORK_DEVICE_IDLE
---

# _PEP_WORK_DEVICE_IDLE structure
The <b>PEP_WORK_DEVICE_IDLE</b> structure indicates whether to ignore the idle time-out for the specified device.

## Syntax
```
typedef struct _PEP_WORK_DEVICE_IDLE {
  POHANDLE DeviceHandle;
  BOOLEAN  IgnoreIdleTimeout;
} PEP_WORK_DEVICE_IDLE, *PPEP_WORK_DEVICE_IDLE;
```

## Members


`DeviceHandle`

A handle that represents the registration of the device with the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx). A POHANDLE value that represents the registration of the device with PoFx. The platform extension plug-in (PEP) previously received this handle from PoFx during the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.

`IgnoreIdleTimeout`

Whether to ignore the idle time-out. Set to TRUE to tell the operating system to ignore the idle time-out for this device. Set to FALSE to tell the operating system to call the device driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh450946">DevicePowerNotRequiredCallback</a> callback routine after the device remains idle for the designated time-out interval. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh439546">PoFxSetDeviceIdleTimeout</a>.

## Remarks
The <b>DeviceIdle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186864">PEP_WORK_INFORMATION</a> structure is a <b>PEP_WORK_DEVICE_IDLE</b> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pepfx.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186864">PEP_WORK_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439546">PoFxSetDeviceIdleTimeout</a>