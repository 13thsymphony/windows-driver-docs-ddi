---
UID : NF:sensorsclassextension.ISensorDriver.OnGetSupportedProperties
title : ISensorDriver::OnGetSupportedProperties method
author : windows-driver-content
description : The ISensorDriver::OnGetSupportedProperties method retrieves the list of properties that the specified sensor provides.
old-location : sensors\isensordriver_ongetsupportedproperties.htm
old-project : sensors
ms.assetid : 8712fe85-0af1-4552-9351-aca4fe5430d1
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : ISensorDriver::OnGetSupportedProperties, OnGetSupportedProperties method [Sensor Devices], ISensorDriver, OnGetSupportedProperties, sensors.isensordriver_ongetsupportedproperties
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SensorConnectionType
req.product : Windows 10 or later.
---


# OnGetSupportedProperties method
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545630">ISensorDriver::OnGetSupportedProperties</a> method retrieves the list of properties that the specified sensor provides.

## Syntax

````
HRESULT OnGetSupportedProperties(
   LPWSTR                          pwszSensorID,
   IPortableDeviceKeyCollection ** ppSupportedProperties
);
````

## Parameters

`pwszSensorID`

LPWSTR that contains the ID for the sensor from which the client application is requesting the properties list.

`ppSupportedProperties`

Address of an IPortableDeviceKeyCollection pointer that receives the list of PROPERTYKEY values that represent the supported properties.


## Return Value

If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## Remarks

Properties describe the sensor device, as opposed to data fields, which contain sensor-generated data. Platform-defined properties are defined in sensors.h.

Each <a href="http://go.microsoft.com/fwlink/p/?linkid=131484">IPortableDeviceKeyCollection</a> object returned in this collection must contain <b>PROPERTYKEY</b>s for the  required properties, as described in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn946698">Sensor Properties</a> reference section.

<a href="http://go.microsoft.com/fwlink/p/?linkid=131484">IPortableDeviceKeyCollection</a> is documented in Windows Portable Devices.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | sensorsclassextension.h |
| **Library** | SensorsClassExtension.lib |