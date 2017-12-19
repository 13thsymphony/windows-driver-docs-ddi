---
UID: NC.sensorscx.EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION
title: EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION
author: windows-driver-content
description: Used to stop a state change notification.
old-location: sensors\evt_sensor_driver_stop_state_change_notification.htm
old-project: sensors
ms.assetid: 53B064AF-D06B-46A0-9D77-2DA72F0B47D6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISensorDriver, ISensorDriver::OnSetProperties, OnSetProperties
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
req.product: Windows 10 or later.
---

# EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION callback



## -description
Used to stop a state change notification.



## -prototype

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


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Sensorscx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
_requires_same_


</td>
</tr>
</table>