---
UID: NF.sensorsclassextension.ISensorDriver.OnClientDisconnect
title: ISensorDriver::OnClientDisconnect method
author: windows-driver-content
description: The ISensorDriver::OnClientDisconnect method notifies the sensor driver that a client application has disconnected.
old-location: sensors\isensordriver_onclientdisconnect.htm
old-project: sensors
ms.assetid: 9484610b-4cbd-4c4e-9e60-ef052702325c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISensorDriver, ISensorDriver::OnClientDisconnect, OnClientDisconnect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 7,Available in Windows 7.
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ISensorDriver.OnClientDisconnect
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
req.product: Windows 10 or later.
---

# ISensorDriver::OnClientDisconnect method



## -description
The <b>ISensorDriver::OnClientDisconnect</b> method notifies the sensor driver that a client application has disconnected.



## -syntax

````
HRESULT OnClientDisconnect(
  [in] IWDFFile           *pClientFile,
  [in] __in_string LPWSTR pwszSensorID
);
````


## -parameters

### -param pClientFile [in]

Pointer to an <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface that represents the file object for the client that disconnected.


### -param pwszSensorID [in]

<b>LPWSTR</b> that contains the ID for the sensor from which the client application is disconnecting.


## -returns
If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.


## -remarks
The sensor class extension calls this method in the following instances:

An application closes normally.

The user revokes permission for an application to access the device that contains the specified sensor.

The cleanup work from a call to <a href="sensors.isensorclassextension_cleanupfile">ISensorClassExtension::CleanupFile</a> has completed.

You can use this call as a signal to update lists and reference counts of connected applications. 

For more information about how to use this method, see <a href="https://msdn.microsoft.com/1895EC5C-08C1-4976-83F2-CD5A2B55338D">Filtering data</a>.

The following example code demonstrates an implementation of <b>ISensorDriver::OnClientDisconnect</b>. This function uses an ATL simple map, named Clients, to keep track of connected clients. See <a href="sensors.isensordriver_onclientconnect">ISensorDriver::OnClientConnect</a> for an example of how connected clients are added to the map.

The ClientData structure is defined as follows.

The function definition follows.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 7

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
None supported

</td>
</tr>
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
Version

</th>
<td width="70%">
Available in Windows 7.

</td>
</tr>
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

## -see-also
<dl>
<dt>
<a href="sensors.isensordriver_onclientconnect">ISensorDriver::OnClientConnect</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20ISensorDriver::OnClientDisconnect method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

