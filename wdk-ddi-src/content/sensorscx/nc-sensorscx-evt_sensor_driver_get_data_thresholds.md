---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS
title: EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS
author: windows-driver-content
description: This callback function returns the thresholds that are associated with a sensor.
old-location: sensors\evtsensorgetdatathresholds.htm
old-project: sensors
ms.assetid: 8D496490-2BB8-49A4-B575-101E61599A65
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS, EvtSensorGetDataThresholds, EvtSensorGetDataThresholds callback function [Sensor Devices], sensors.evtsensorgetdatathresholds, sensorscx/EvtSensorGetDataThresholds
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
-	EvtSensorGetDataThresholds
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---


# EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS callback function
This callback function returns the thresholds that are associated with a sensor.

## Syntax

```
EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS EvtSensorDriverGetDataThresholds;

_IRQL_requires_same_ NTSTATUS EvtSensorDriverGetDataThresholds(
  SENSOROBJECT Sensor,
  PSENSOR_COLLECTION_LIST pThresholds,
  PULONG pSize
)
{...}
```

## Parameters

`Sensor`

A reference to a sensor object.

`pThresholds`

A list of threshold properties and their values associated with the <b>Sensor</b>. For more information, see <a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>.

`pSize`




## Return Value

This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to 
		  determine if the call to the driver’s Evt function was successful, 
		  but does not take any action if the function failed or does not return STATUS_SUCCESS.

## Remarks

This function must be implemented by the driver and is called by the class extension.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | sensorscx.h |
| **IRQL** | "_requires_same_" |

## See Also

<a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>