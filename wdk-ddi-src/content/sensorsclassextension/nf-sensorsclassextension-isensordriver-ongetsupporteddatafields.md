---
UID: NF:sensorsclassextension.ISensorDriver.OnGetSupportedDataFields
title: ISensorDriver::OnGetSupportedDataFields method
author: windows-driver-content
description: The ISensorDriver::OnGetSupportedDataFields method retrieves the list of data fields that the specified sensor can provide.
old-location: sensors\isensordriver_ongetsupporteddatafields.htm
old-project: sensors
ms.assetid: 5020212e-9e3f-468f-8f7c-77d70a8f024b
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: sensors.isensordriver_ongetsupporteddatafields, OnGetSupportedDataFields method [Sensor Devices], OnGetSupportedDataFields, ISensorDriver, ISensorDriver::OnGetSupportedDataFields
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Windows
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
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	SensorsClassExtension.lib
-	SensorsClassExtension.dll
apiname:
-	OnGetSupportedDataFields
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---


# OnGetSupportedDataFields method
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545620">ISensorDriver::OnGetSupportedDataFields</a> method retrieves the list of data fields that the specified sensor can provide.

## Syntax

````
HRESULT OnGetSupportedDataFields(
   LPWSTR                          pwszSensorID,
   IPortableDeviceKeyCollection ** ppSupportedDataFields
);
````

## Parameters

`pwszSensorID`

LPWSTR that contains the ID for the sensor from which the client application is requesting the data fields list.

`ppSupportedDataFields`

Address of an IPortableDeviceKeyCollection pointer that receives the list of PROPERTYKEY values that represent the supported data fields.


## Return Value

If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## Remarks

Data fields contain sensor-generated data, as opposed to properties, which describe the sensor device. Platform-defined data fields are defined in sensors.h.

All drivers must support SENSOR_DATA_TYPE_TIMESTAMP as a required data field.

<a href="http://go.microsoft.com/fwlink/p/?linkid=131484">IPortableDeviceKeyCollection</a> is documented in Windows Portable Devices.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | sensorsclassextension.h |
| **Library** | SensorsClassExtension.lib |