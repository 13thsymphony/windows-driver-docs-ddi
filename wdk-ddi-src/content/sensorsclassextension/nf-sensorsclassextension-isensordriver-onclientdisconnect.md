---
UID : NF:sensorsclassextension.ISensorDriver.OnClientDisconnect
title : ISensorDriver::OnClientDisconnect method
author : windows-driver-content
description : The ISensorDriver::OnClientDisconnect method notifies the sensor driver that a client application has disconnected.
old-location : sensors\isensordriver_onclientdisconnect.htm
old-project : sensors
ms.assetid : 9484610b-4cbd-4c4e-9e60-ef052702325c
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : ISensorDriver, OnClientDisconnect, sensorsclassextension/ISensorDriver::OnClientDisconnect, ISensorDriver::OnClientDisconnect, sensors.isensordriver_onclientdisconnect, ISensorDriver interface [Sensor Devices], OnClientDisconnect method, OnClientDisconnect method [Sensor Devices], ISensorDriver interface, OnClientDisconnect method [Sensor Devices], Sensor_IFaces_f5f91a04-84b3-4302-9c26-845281651ed9.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : sensorsclassextension.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Windows 7,Available in Windows 7.
req.target-min-winversvr : None supported
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


# OnClientDisconnect method
The <b>ISensorDriver::OnClientDisconnect</b> method notifies the sensor driver that a client application has disconnected.

## Syntax

````
HRESULT OnClientDisconnect(
  [in] IWDFFile           *pClientFile,
  [in] __in_string LPWSTR pwszSensorID
);
````

## Parameters

`pClientFile`

Pointer to an <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface that represents the file object for the client that disconnected.

`pwszSensorID`

<b>LPWSTR</b> that contains the ID for the sensor from which the client application is disconnecting.


## Return Value

If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## Remarks

The sensor class extension calls this method in the following instances:
<ul>
<li>
An application closes normally.

</li>
<li>
The user revokes permission for an application to access the device that contains the specified sensor.

</li>
<li>
The cleanup work from a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545512">ISensorClassExtension::CleanupFile</a> has completed.

</li>
</ul>You can use this call as a signal to update lists and reference counts of connected applications. 

For more information about how to use this method, see <a href="https://msdn.microsoft.com/1895EC5C-08C1-4976-83F2-CD5A2B55338D">Filtering data</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 7,Available in Windows 7. Windows 7,Available in Windows 7. |
| **Target Platform** | Desktop |
| **Header** | sensorsclassextension.h |
| **Library** | SensorsClassExtension.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545573">ISensorDriver::OnClientConnect</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20ISensorDriver::OnClientDisconnect method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>