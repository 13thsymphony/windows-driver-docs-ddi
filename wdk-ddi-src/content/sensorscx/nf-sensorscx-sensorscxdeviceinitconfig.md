---
UID: NF:sensorscx.SensorsCxDeviceInitConfig
title: SensorsCxDeviceInitConfig function
author: windows-driver-content
description: This function configures the sensor device.
old-location: sensors\sensorscxdeviceinitconfig.htm
old-project: sensors
ms.assetid: E347F2E1-5AF5-411A-8F05-DA4826240E02
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SensorsCxDeviceInitConfig function [Sensor Devices], sensors.sensorscxdeviceinitconfig, sensorscx/SensorsCxDeviceInitConfig, SensorsCxDeviceInitConfig
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	SensorsCx.h
apiname:
-	SensorsCxDeviceInitConfig
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---


# SensorsCxDeviceInitConfig function
This function configures the sensor device.

## Syntax

````
FORCEINLINE NTSTATUS SensorsCxDeviceInitConfig(
  _Inout_ PWDFDEVICE_INIT        pFxDeviceInit,
  _Inout_ PWDF_OBJECT_ATTRIBUTES pFdoAttributes,
  _In_    ULONG                  Flags
);
````

## Parameters

`pFxDeviceInit`

A reference to WDFDEVICE_INIT.

`pFdoAttributes`

A reference to WDF_OBJECT_ATTRIBUTES.

`Flags`

The flags for the sensor driver. Reserved set to 0.


## Return Value

This function returns STATUS_SUCCESS when completed successfully. When an invalid parameter is supplied or this function fails, STATUS_INVALID_PARAMETER is returned. This function can also return other NTSTATUS values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sensorscx.h |
| **Library** | NtosKrnl.exe |