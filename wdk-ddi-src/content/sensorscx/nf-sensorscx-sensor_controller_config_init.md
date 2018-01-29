---
UID : NF:sensorscx.SENSOR_CONTROLLER_CONFIG_INIT
title : SENSOR_CONTROLLER_CONFIG_INIT function
author : windows-driver-content
description : This function initializes a SENSOR_CONTROLLER_CONFIG structure.
old-location : sensors\sensor_controller_config_init.htm
old-project : sensors
ms.assetid : 68A0A777-C068-4CE2-AB75-B977B34079C0
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : SENSOR_CONTROLLER_CONFIG_INIT function [Sensor Devices], SENSOR_CONTROLLER_CONFIG_INIT, sensors.sensor_controller_config_init, sensorscx/SENSOR_CONTROLLER_CONFIG_INIT
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


# SENSOR_CONTROLLER_CONFIG_INIT function
This function initializes a <a href="..\sensorscx\ns-sensorscx-_sensor_controller_config.md">SENSOR_CONTROLLER_CONFIG</a> structure.

## Syntax

````
FORCEINLINE VOID SENSOR_CONTROLLER_CONFIG_INIT(
  _Out_ PSENSOR_CONTROLLER_CONFIG pConfig
);
````

## Parameters

`pConfig`

A pointer to a new <a href="..\sensorscx\ns-sensorscx-_sensor_controller_config.md">SENSOR_CONTROLLER_CONFIG</a> structure.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sensorscx.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\sensorscx\ns-sensorscx-_sensor_controller_config.md">SENSOR_CONTROLLER_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20SENSOR_CONTROLLER_CONFIG_INIT function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>