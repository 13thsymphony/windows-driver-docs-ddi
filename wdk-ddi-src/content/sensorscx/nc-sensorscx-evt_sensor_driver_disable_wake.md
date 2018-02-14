---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_DISABLE_WAKE
title: EVT_SENSOR_DRIVER_DISABLE_WAKE
author: windows-driver-content
description: Callback to disable wake for the sensor.
old-location: sensors\evt_sensor_driver_disable_wake.htm
old-project: sensors
ms.assetid: 15873D33-1423-47D7-8CE6-F2012241B658
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: sensors.evt_sensor_driver_disable_wake, EVT_SENSOR_DRIVER_DISABLE_WAKE callback function [Sensor Devices], EVT_SENSOR_DRIVER_DISABLE_WAKE, sensorscx/EVT_SENSOR_DRIVER_DISABLE_WAKE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sensorscx.h
req.include-header: 
req.target-type: Windows
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
req.irql: "_requires_same_"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	SensorsCx.h
apiname:
-	EVT_SENSOR_DRIVER_DISABLE_WAKE
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---


# EVT_SENSOR_DRIVER_DISABLE_WAKE function
Callback to disable wake for the sensor.

## Syntax

```
EVT_SENSOR_DRIVER_DISABLE_WAKE EvtSensorDriverDisableWake;

_IRQL_requires_same_ NTSTATUS EvtSensorDriverDisableWake(
  SENSOROBJECT Sensor
)
{...}
```

## Parameters

`Sensor`

A reference to the sensor object


## Return Value

This function returns STATUS_SUCCESS when completed successfully.

<div class="alert"><b>Note</b>  The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.</div>
<div> </div>

## Remarks

This DDSI function does not compulsorily have to be implemented by the driver because it is expected that some sensor drivers do not care about disabling wake on the sensor. If it not implemented the enable call is ignored and a STATUS_SUCCESS is returned. This is primarily because PKEY_Sensor_WakeCapable is implemented today and used by some sensors such as the accelerometer and the proximity sensor, and for backward compatibility, implementing this DDSI is optional.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | sensorscx.h |
| **IRQL** | "_requires_same_" |