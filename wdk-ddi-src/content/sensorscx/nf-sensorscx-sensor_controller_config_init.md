---
UID: NF:sensorscx.SENSOR_CONTROLLER_CONFIG_INIT
title: SENSOR_CONTROLLER_CONFIG_INIT function
author: windows-driver-content
description: This function initializes a SENSOR_CONTROLLER_CONFIG structure.
old-location: sensors\sensor_controller_config_init.htm
old-project: sensors
ms.assetid: 68A0A777-C068-4CE2-AB75-B977B34079C0
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: SENSOR_CONTROLLER_CONFIG_INIT, SENSOR_CONTROLLER_CONFIG_INIT function [Sensor Devices], sensors.sensor_controller_config_init, sensorscx/SENSOR_CONTROLLER_CONFIG_INIT
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
-	SENSOR_CONTROLLER_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---


# SENSOR_CONTROLLER_CONFIG_INIT function
This function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/dn957098">SENSOR_CONTROLLER_CONFIG</a> structure.

## Syntax

```
void SENSOR_CONTROLLER_CONFIG_INIT(
  PSENSOR_CONTROLLER_CONFIG pConfig
);
```

## Parameters

`pConfig`

A pointer to a new <a href="https://msdn.microsoft.com/library/windows/hardware/dn957098">SENSOR_CONTROLLER_CONFIG</a> structure.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sensorscx.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn957098">SENSOR_CONTROLLER_CONFIG</a>