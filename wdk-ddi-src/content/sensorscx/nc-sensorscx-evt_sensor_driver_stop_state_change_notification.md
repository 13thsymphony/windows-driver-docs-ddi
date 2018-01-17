---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION
title: EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION function
author: windows-driver-content
description: Used to stop a state change notification.
old-location: sensors\evt_sensor_driver_stop_state_change_notification.htm
old-project: sensors
ms.assetid: 53B064AF-D06B-46A0-9D77-2DA72F0B47D6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sensorscx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFN_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION
req.alt-loc: sensorscx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _requires_same_
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION function



## -description
Used to stop a state change notification.



## -syntax

````
NTSTATUS EvtSensorDriverStopStateChangeNotification(
   SENSOROBJECT Sensors
);
````


## -parameters

### -param Sensors 

Holds information on the sensor being handled by the driver.


## -returns
Returns STATUS_SUCCESS if completed successfully.


## -remarks
