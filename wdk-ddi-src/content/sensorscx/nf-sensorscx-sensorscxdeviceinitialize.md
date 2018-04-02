---
UID: NF:sensorscx.SensorsCxDeviceInitialize
title: SensorsCxDeviceInitialize function
author: windows-driver-content
description: This function initializes the sensor in the class extension.
old-location: sensors\sensorscxdeviceinitialize.htm
old-project: sensors
ms.assetid: F6F758AC-5C8C-4226-B906-972C5BCD7A3E
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: SensorsCxDeviceInitialize, SensorsCxDeviceInitialize function [Sensor Devices], sensors.sensorscxdeviceinitialize, sensorscx/SensorsCxDeviceInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sensorscx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	SensorsCx.h
api_name:
-	SensorsCxDeviceInitialize
product:
- Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---


# SensorsCxDeviceInitialize function
This function initializes the sensor in the class extension.

## Syntax

```
NTSTATUS SensorsCxDeviceInitialize(
  WDFDEVICE                 FxDevice,
  PSENSOR_CONTROLLER_CONFIG pSensorConfig
);
```

## Parameters

`FxDevice`

A WDFDEVICE handle to the framework device object that represents the sensor.

`pSensorConfig`

A list of functions that the driver implements. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn957098">SENSOR_CONTROLLER_CONFIG</a>.


## Return Value

This function returns STATUS_SUCCESS when completed successfully. When an invalid parameter is supplied or this function fails, STATUS_INVALID_PARAMETER is returned. Other NTSTATUS values can also be returned.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sensorscx.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn957098">SENSOR_CONTROLLER_CONFIG</a>