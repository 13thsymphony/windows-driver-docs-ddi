---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS
title: EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS
author: windows-driver-content
description: This callback function handles IOCTLs outside of the class extension.
old-location: sensors\evtsensordeviceiocontrol.htm
old-project: sensors
ms.assetid: 8AA23EEF-310B-4989-B41A-0A178886DC6D
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS, EvtSensorSetDataThresholds, EvtSensorSetDataThresholds callback function [Sensor Devices], sensors.evtsensordeviceiocontrol, sensorscx/EvtSensorSetDataThresholds
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	SensorsCx.h
api_name:
-	EvtSensorSetDataThresholds
product:
- Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---


# EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS callback function
This callback function handles IOCTLs outside of the class extension.

## Syntax

```
EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS EvtSensorDriverSetDataThresholds;

_IRQL_requires_same_ NTSTATUS EvtSensorDriverSetDataThresholds(
  SENSOROBJECT Sensor,
  PSENSOR_COLLECTION_LIST pThresholds
)
{...}
```

## Parameters

`Sensor`

A reference to a sensor object.

`pThresholds`




## Return Value

This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.

## Remarks

This function is implemented by the driver and is called by the class extension. The driver is responsible for interfacing with the driver framework and resolving the IRP for IOCTLs that are forwarded to this function.

<b>Note</b> If the driver needs to queue the IRP, it must copy the IRP to an IoQueue that the driver owns. This will prevent all IRPs for the driver to be stalled until completion.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | sensorscx.h |
| **IRQL** | "_requires_same_" |