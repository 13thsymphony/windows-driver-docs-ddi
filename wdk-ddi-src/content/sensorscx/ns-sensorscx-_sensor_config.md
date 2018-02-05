---
UID : NS:sensorscx._SENSOR_CONFIG
title : "_SENSOR_CONFIG"
author : windows-driver-content
description : This structure contains information that the sensor driver passes to the class extension about each sensor.
old-location : sensors\sensor_config.htm
old-project : sensors
ms.assetid : E21E2FEC-8733-4A8A-A0C4-899F10824F9B
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : PSENSOR_CONFIG, SENSOR_CONFIG, sensorscx/SENSOR_CONFIG, *PSENSOR_CONFIG, _SENSOR_CONFIG, sensors.sensor_config, sensorscx/PSENSOR_CONFIG, SENSOR_CONFIG structure [Sensor Devices], PSENSOR_CONFIG structure pointer [Sensor Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : sensorscx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SENSOR_CONFIG, *PSENSOR_CONFIG
req.product : Windows 10 or later.
---

# _SENSOR_CONFIG structure
This structure contains information that the sensor driver passes to the class extension about each sensor.

## Syntax
````
typedef struct _SENSOR_CONFIG {
  ULONG                   Size;
  PSENSOR_COLLECTION_LIST pEnumerationList;
} SENSOR_CONFIG, *PSENSOR_CONFIG;
````

## Members


`pEnumerationList`

The list of enumerations. For more information, see <a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>.

`Size`

The allocated size of this structure (in bytes).

## Remarks
The SENSOR_CONFIG structure works with the following helper function:
<ul>
<li>
<a href="..\sensorscx\nf-sensorscx-sensor_config_init.md">SENSOR_CONFIG_INIT</a>
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | sensorscx.h |