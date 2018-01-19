---
UID : NF:sensorsclassextension.ISensorDriver.OnClientSubscribeToEvents
title : ISensorDriver::OnClientSubscribeToEvents method
author : windows-driver-content
description : The ISensorDriver::OnClientSubscribeToEvents method notifies the sensor driver that an authorized client application is requesting event notifications.
old-location : sensors\isensordriver_onclientsubscribetoevents.htm
old-project : sensors
ms.assetid : b0528932-d7a8-46d7-bd94-6fd729a9d7f2
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : ISensorDriver, ISensorDriver::OnClientSubscribeToEvents, OnClientSubscribeToEvents
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : sensorsclassextension.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : OnClientSubscribeToEvents
req.alt-loc : SensorsClassExtension.lib,SensorsClassExtension.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : SensorsClassExtension.lib
req.dll : 
req.irql : 
req.typenames : SensorConnectionType
req.product : Windows 10 or later.
---


# OnClientSubscribeToEvents method
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545589">ISensorDriver::OnClientSubscribeToEvents</a> method notifies the sensor driver that an authorized client application is requesting event notifications.

## Syntax

````
HRESULT OnClientSubscribeToEvents(
   IWDFFile * pClientFile,
   LPWSTR     pwszSensorID
);
````

## Parameters

`pClientFile`

Pointer to an IWDFFile interface that represents the file object for the application requesting event notifications.

`pwszSensorID`

LPWSTR that contains the ID for the sensor from which the client application is requesting event notifications.


## Return Value

If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## Remarks

When a client application requests event notifications, the driver raises all events to the sensor class extension for the specified object ID. The class extension then forwards these events to the Sensor API as event notifications for applications. 

You can maintain a reference count of connected applications for each sensor to avoid making event callbacks when not required. 

Platform-defined events are defined in sensors.h.

For more information about how to use this method, see <a href="https://msdn.microsoft.com/1895EC5C-08C1-4976-83F2-CD5A2B55338D">Filtering data</a>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sensorsclassextension.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |