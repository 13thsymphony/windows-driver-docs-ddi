---
UID : NF:sensorscx.SensorsCxSensorInitialize
title : SensorsCxSensorInitialize function
author : windows-driver-content
description : This function sets the enumeration properties of a sensor.
old-location : sensors\sensorscxsensorinitialize.htm
old-project : sensors
ms.assetid : D6C0B66A-58ED-4E1D-89E2-4A1AF77281C1
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : SensorsCxSensorInitialize function [Sensor Devices], sensorscx/SensorsCxSensorInitialize, sensors.sensorscxsensorinitialize, SensorsCxSensorInitialize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : sensorscx.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SensorConnectionType
req.product : Windows 10 or later.
---


# SensorsCxSensorInitialize function
This function sets the enumeration properties of a sensor.

 For more information about sensor properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn957027">Enumeration properties</a>.

## Syntax

````
FORCEINLINE NTSTATUS SensorsCxSensorInitialize(
  _In_ SENSOROBJECT   Sensor,
  _In_ PSENSOR_CONFIG pSensorConfig
);
````

## Parameters

`Sensor`

A reference to a sensor object.

`pSensorConfig`

A list of enumeration properties. For more information, see <a href="..\sensorscx\ns-sensorscx-_sensor_config.md">SENSOR_CONFIG</a>.


## Return Value

This function returns NTSTATUS with different values. Some values that may be returned are the following:
<ul>
<li>
STATUS_SUCCESS is returned when the function completes successfully.

</li>
<li>
STATUS_INVALID_PARAMETER is returned if any of the _In_ parameters are NULL or the <b>pSensorConfig-&gt;pEnumerationList-&gt;Count</b> variable is 0 or too big.

</li>
<li>
STATUS_BUFFER_TOO_SMALL is returned if the <b>pSensorConfig</b> buffer is smaller than the size of the <a href="..\sensorscx\ns-sensorscx-_sensor_config.md">SENSOR_CONFIG</a> structure.

</li>
<li>
STATUS_NOT_FOUND is returned if there was an error constructing the controller object context from the <b>Sensor</b> object.

</li>
</ul>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sensorscx.h |
| **Library** | NtosKrnl.exe |