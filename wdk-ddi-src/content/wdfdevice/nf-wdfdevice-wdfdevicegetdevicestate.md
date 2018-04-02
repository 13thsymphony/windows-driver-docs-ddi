---
UID: NF:wdfdevice.WdfDeviceGetDeviceState
title: WdfDeviceGetDeviceState function
author: windows-driver-content
description: The WdfDeviceGetDeviceState method retrieves the device state for a specified device.
old-location: wdf\wdfdevicegetdevicestate.htm
old-project: wdf
ms.assetid: 510197cf-8eab-4e1a-8b51-c1c08c58532b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_459b9aad-7503-4319-be67-4b713a32559e.xml, WdfDeviceGetDeviceState, WdfDeviceGetDeviceState method, kmdf.wdfdevicegetdevicestate, wdf.wdfdevicegetdevicestate, wdfdevice/WdfDeviceGetDeviceState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDeviceGetDeviceState
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceGetDeviceState function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceGetDeviceState</b> method retrieves the device state for a specified device.

## Syntax

```
void WdfDeviceGetDeviceState(
  WDFDEVICE         Device,
  PWDF_DEVICE_STATE DeviceState
);
```

## Parameters

`Device`

A handle to a framework device object.

`DeviceState`

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551284">WDF_DEVICE_STATE</a> structure that receives the device's state information.


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551286">WDF_DEVICE_STATE_INIT</a>