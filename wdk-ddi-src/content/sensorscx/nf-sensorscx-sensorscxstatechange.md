---
UID: NF:sensorscx.SensorsCxStateChange
title: SensorsCxStateChange function
author: windows-driver-content
description: Used to initialize a state change.
old-location: sensors\sensorscxstatechange.htm
old-project: sensors
ms.assetid: E6897994-51C7-4278-9CCE-9B7E9DD408D7
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: SensorsCxStateChange, SensorsCxStateChange function [Sensor Devices], sensors.sensorscxstatechange, sensorscx/SensorsCxStateChange
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
-	SensorsCxStateChange
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---


# SensorsCxStateChange function
Used to initialize a state change.

## Syntax

```
void SensorsCxStateChange(
  SENSOROBJECT Sensor,
  SENSOR_STATE State
);
```

## Parameters

`Sensor`

Holds information on the sensor being managed by the driver.

`State`

Holds information on the state of the sensor.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sensorscx.h |