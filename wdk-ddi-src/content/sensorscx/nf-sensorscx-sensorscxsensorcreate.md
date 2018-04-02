---
UID: NF:sensorscx.SensorsCxSensorCreate
title: SensorsCxSensorCreate function
author: windows-driver-content
description: This function creates an instance of a sensor in the class extension.
old-location: sensors\sensorscxsensorcreate.htm
old-project: sensors
ms.assetid: A365381B-3456-47B6-93C7-81C8963CB183
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: SensorsCxSensorCreate, SensorsCxSensorCreate function [Sensor Devices], sensors.sensorscxsensorcreate, sensorscx/SensorsCxSensorCreate
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
-	SensorsCxSensorCreate
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---


# SensorsCxSensorCreate function
This function creates an instance of a sensor in the class extension.

## Syntax

```
NTSTATUS SensorsCxSensorCreate(
  WDFDEVICE              FxDevice,
  PWDF_OBJECT_ATTRIBUTES pSensorAttributes,
  PSENSOROBJECT          pSensor
);
```

## Parameters

`FxDevice`

A WDFDEVICE handle to the framework device object that represents the sensor.

`pSensorAttributes`

A reference to <a href="http://go.microsoft.com/fwlink/p/?linkid=313456">WDF_OBJECT_ATTRIBUTES</a>.

`pSensor`

A reference to a sensor object that is used within the class extension.


## Return Value

This function returns NTSTATUS with different values. Some values that may be returned are the following:

<ul>
<li>
STATUS_SUCCESS is returned when the function completes successfully.

</li>
<li>
STATUS_INVALID_PARAMETER is returned if any of the _In_ parameters are NULL.

</li>
<li>
STATUS_INSUFFICIENT_RESOURCES is returned if there were insufficient resources to allocate memory for this function.

</li>
</ul>

## Remarks

SensorsCxSensorCreate is implemented by the class extension and must be called by the driver. 



<div class="alert"><b>Note</b>  If pSensorAttributes-&gt;ParentObject is not set to NULL or FxDevice, then SensorsCxSensorCreate will fail. If pSensorAttributes-&gt;ParentObject is NULL, then the class extension (CX) will set it to FxDevice.</div>
<div> </div>
 

The sensors class extension writes a set of properties for each sensor when SensorsCxSensorCreate. For information about these properties, see Enumeration properties.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sensorscx.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn957027">Enumeration properties</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=313456">WDF_OBJECT_ATTRIBUTES</a>