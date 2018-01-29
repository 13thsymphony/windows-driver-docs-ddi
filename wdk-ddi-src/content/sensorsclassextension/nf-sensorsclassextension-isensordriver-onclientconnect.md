---
UID : NF:sensorsclassextension.ISensorDriver.OnClientConnect
title : ISensorDriver::OnClientConnect method
author : windows-driver-content
description : The ISensorDriver::OnClientConnect method notifies the sensor driver that a client application has connected.
old-location : sensors\isensordriver_onclientconnect.htm
old-project : sensors
ms.assetid : 0f64288b-5100-4529-af2f-3e867375da39
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : OnClientConnect method [Sensor Devices], OnClientConnect, ISensorDriver::OnClientConnect, sensors.isensordriver_onclientconnect, ISensorDriver
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


# OnClientConnect method
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545573">ISensorDriver::OnClientConnect</a> method notifies the sensor driver that a client application has connected.

## Syntax

````
HRESULT OnClientConnect(
   IWDFFile * pClientFile,
   LPWSTR     pwszSensorID
);
````

## Parameters

`pClientFile`

Pointer to an IWDFFile interface that represents the file object for the application requesting the connection.

`pwszSensorID`

LPWSTR that contains the ID for the sensor to which the client application is connecting.


## Return Value

If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## Remarks

The sensor class extension calls this method only if the specified client application has been given permission by the user to access the driver. If the user revokes this permission, the class extension immediately calls <a href="https://msdn.microsoft.com/9484610b-4cbd-4c4e-9e60-ef052702325c">ISensorDriver::OnClientDisconnect</a> for the same application/sensor pair.

The class extension always calls this method before calling <a href="https://msdn.microsoft.com/7c3cca5b-1d08-42dc-8dc4-42eb1160b8bb">ISensorDriver::OnSetProperties</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545607">ISensorDriver::OnGetDataFields</a> for a particular sensor. We recommend that you maintain a reference count of connected applications to help to anticipate when calls to these three methods are possible. If no client applications are connected, you may want to change the behavior of the driver, for example, by taking steps to reduce power consumption.

You can use the pointer value (the address pointed to) provided by <i>pClientFile</i> as a kind of ID to keep track of connected applications. However, you must track these IDs separately for each sensor, not for each device, because the class extension may provide the same pointer value to multiple sensors on the same device.

For more information about how to use this method, see <a href="https://msdn.microsoft.com/1895EC5C-08C1-4976-83F2-CD5A2B55338D">Filtering data</a>.

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