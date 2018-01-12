---
UID: NF:sensorsclassextension.ISensorDriver.OnGetSupportedSensorObjects
title: ISensorDriver::OnGetSupportedSensorObjects method
author: windows-driver-content
description: The ISensorDriver::OnGetSupportedSensorObjects method retrieves the list of sensors that the driver provides.
old-location: sensors\isensordriver_ongetsupportedsensorobjects.htm
old-project: sensors
ms.assetid: a8ea63cf-24ba-467b-9c27-ab8e38be1c04
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISensorDriver, ISensorDriver::OnGetSupportedSensorObjects, OnGetSupportedSensorObjects
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
req.alt-api: OnGetSupportedSensorObjects
req.alt-loc: SensorsClassExtension.lib,SensorsClassExtension.dll
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
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# ISensorDriver::OnGetSupportedSensorObjects method



## -description
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545633">ISensorDriver::OnGetSupportedSensorObjects</a> method retrieves the list of sensors that the driver provides.



## -syntax

````
HRESULT OnGetSupportedSensorObjects(
   IPortableDeviceValuesCollection ** ppSensorObjectCollection
);
````


## -parameters

### -param ppSensorObjectCollection 

Address of an IPortableDeviceValuesCollection pointer that receives the list of sensors.


## -returns
If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Sensorsclassextension.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>SensorsClassExtension.lib</dt>
</dl>
</td>
</tr>
</table>