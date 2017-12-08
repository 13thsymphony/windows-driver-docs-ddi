---
UID: NF.sensorscx.SensorsCxDeviceInitialize
title: SensorsCxDeviceInitialize function
author: windows-driver-content
description: This function initializes the sensor in the class extension.
old-location: sensors\sensorscxdeviceinitialize.htm
old-project: sensors
ms.assetid: F6F758AC-5C8C-4226-B906-972C5BCD7A3E
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SensorsCxDeviceInitialize
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
req.alt-api: SensorsCxDeviceInitialize
req.alt-loc: SensorsCx.h
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
req.product: Windows 10 or later.
---

# SensorsCxDeviceInitialize function



## -description
This function initializes the sensor in the class extension.


## -syntax

````
FORCEINLINE NTSTATUS SensorsCxDeviceInitialize(
  _In_ WDFDEVICE                 FxDevice,
  _In_ PSENSOR_CONTROLLER_CONFIG pSensorConfig
);
````


## -parameters

### -param FxDevice [in]

A WDFDEVICE handle to the framework device object that represents the sensor.

### -param pSensorConfig [in]

A list of functions that the driver implements. For more information, see <a href="sensors.sensor_controller_config">SENSOR_CONTROLLER_CONFIG</a>.

## -returns
This function returns STATUS_SUCCESS when completed successfully. When an invalid parameter is supplied or this function fails, STATUS_INVALID_PARAMETER is returned. Other NTSTATUS values can also be returned.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>SensorsCx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="sensors.sensor_controller_config">SENSOR_CONTROLLER_CONFIG</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20SensorsCxDeviceInitialize function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
