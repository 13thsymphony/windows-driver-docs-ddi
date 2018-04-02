---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS
title: EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS
author: windows-driver-content
description: This callback function returns a list of data fields supported by the specified sensor.
old-location: sensors\evtsensorgetsupporteddatafields.htm
old-project: sensors
ms.assetid: 8C73DFE2-E87A-460D-8EBE-CF3767CAA23F
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS, EvtSensorGetSupportedDataFields, EvtSensorGetSupportedDataFields callback function [Sensor Devices], sensors.evtsensorgetsupporteddatafields, sensorscx/EvtSensorGetSupportedDataFields
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
-	EvtSensorGetSupportedDataFields
product:
- Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---


# EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS callback function
This callback function returns a list of data fields supported by the specified sensor.

For more information about data fields, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn946691">Sensor data fields</a>.

## Syntax

```
EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS EvtSensorDriverGetSupportedDataFields;

_IRQL_requires_same_ NTSTATUS EvtSensorDriverGetSupportedDataFields(
  SENSOROBJECT Sensor,
  PSENSOR_PROPERTY_LIST pDataFields,
  PULONG pSize
)
{...}
```

## Parameters

`Sensor`

A reference to a sensor object.

`pDataFields`

A list of data fields that are supported by the given <b>Sensor</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn946699">SENSOR_PROPERTY_LIST</a>.

`pSize`

The size of <b>pFields</b>.


## Return Value

This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.

## Remarks

This function must be implemented by the driver and is called by the class extension.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | sensorscx.h |
| **IRQL** | "_requires_same_" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946699">SENSOR_PROPERTY_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn946691">Sensor data fields</a>