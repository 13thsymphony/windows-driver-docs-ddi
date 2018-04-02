---
UID: NS:wdfdevice._WDF_DEVICE_POWER_NOTIFICATION_DATA
title: "_WDF_DEVICE_POWER_NOTIFICATION_DATA"
author: windows-driver-content
description: The WDF_DEVICE_POWER_NOTIFICATION_DATA structure describes a state change within a device's power state machine.
old-location: wdf\wdf_device_power_notification_data.htm
old-project: wdf
ms.assetid: 23fb912b-58c2-4f76-8173-f4125174a149
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_afff2c28-e176-47c7-b1f2-8e8986b9f29d.xml, WDF_DEVICE_POWER_NOTIFICATION_DATA, WDF_DEVICE_POWER_NOTIFICATION_DATA structure, _WDF_DEVICE_POWER_NOTIFICATION_DATA, kmdf.wdf_device_power_notification_data, wdf.wdf_device_power_notification_data, wdfdevice/WDF_DEVICE_POWER_NOTIFICATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_DEVICE_POWER_NOTIFICATION_DATA
product:
- Windows
targetos: Windows
req.typenames: WDF_DEVICE_POWER_NOTIFICATION_DATA
req.product: Windows 10 or later.
---

# _WDF_DEVICE_POWER_NOTIFICATION_DATA structure
<p class="CCE_Message">[Applies to KMDF only]

The WDF_DEVICE_POWER_NOTIFICATION_DATA structure describes a state change within a device's power state machine.

## Syntax
```
typedef struct _WDF_DEVICE_POWER_NOTIFICATION_DATA {
  WDF_STATE_NOTIFICATION_TYPE Type;
  union {
    struct {
      WDF_DEVICE_POWER_STATE CurrentState;
      WDF_DEVICE_POWER_STATE NewState;
    } EnterState;
    struct {
      WDF_DEVICE_POWER_STATE CurrentState;
    } PostProcessState;
    struct {
      WDF_DEVICE_POWER_STATE CurrentState;
      WDF_DEVICE_POWER_STATE NewState;
    } LeaveState;
  } Data;
} WDF_DEVICE_POWER_NOTIFICATION_DATA;
```

## Members


`Type`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552513">WDF_STATE_NOTIFICATION_TYPE</a>-typed enumerator that identifies the type of state change that is being reported.

`Data`



## Remarks
The <b>WDF_DEVICE_POWER_NOTIFICATION_DATA</b> structure is an input argument to a driver's <a href="https://msdn.microsoft.com/9f54c7e2-0c8a-46ee-9318-6db934c1aab6">EvtDevicePowerStateChange</a> callback function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdevice.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546071">WdfDeviceInitRegisterPowerStateChangeCallback</a>