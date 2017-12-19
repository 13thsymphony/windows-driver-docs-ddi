---
UID: NF.sensorsclassextension.ISensorClassExtension.ProcessIoControl
title: ISensorClassExtension::ProcessIoControl method
author: windows-driver-content
description: The ISensorClassExtension::ProcessControl method sends Windows Portable Devices (WPD) I/O control requests to the sensor class extension for processing.
old-location: sensors\isensorclassextension_processiocontrol.htm
old-project: sensors
ms.assetid: bd886086-4e23-47c0-ae58-9234399e5a79
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISensorClassExtension, ISensorClassExtension::ProcessIoControl, ProcessIoControl
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
req.alt-api: ProcessIoControl
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

# ISensorClassExtension::ProcessIoControl method



## -description
The <a href="sensors.isensorclassextension_processiocontrol">ISensorClassExtension::ProcessControl</a> method sends Windows Portable Devices (WPD) I/O control requests to the sensor class extension for processing.



## -syntax

````
HRESULT ProcessIoControl(
   IWDFIoRequest * pRequest
);
````


## -parameters

### -param pRequest 

Pointer to the IWDFIoRequest interface that represents the UMDF request object.


## -returns
This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method succeeded.
<dl>
<dt><b>E_ACCESS_DENIED</b></dt>
</dl>No permission. For example, the I/O request sought data for which no permission exists.
<dl>
<dt><b>E_POINTER</b></dt>
</dl>A required pointer argument was <b>NULL</b>.
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_SUPPORTED)</b></dt>
</dl>The request did not contain a WPD IOCTL.

 


## -remarks
UMDF sends I/O control requests to sensor drivers through <a href="umdf.iqueuecallbackdeviceiocontrol_ondeviceiocontrol">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a>. We recommend that you call ProcessIoControl to forward all WPD requests to the sensor class extension for processing. You can use the WPD macro IS_WPD_IOCTL to determine whether a given control code is specific to WPD. Clients of the Sensor API and Location API send only WPD IOCTLs, which can always be process by the sensor class extension.

After processing an I/O control request, the sensor class extension uses the driver's callback interface, <a href="..\sensorsclassextension\nn-sensorsclassextension-isensordriver.md">ISensorDriver</a>, to provide notifications, as appropriate. WPD requests that the sensor class extension does not handle by default are sent to the driver through <a href="sensors.isensordriver_onprocesswpdmessage">ISensorDriver::OnProcessWpdMessage</a>.

The driver must not complete I/O control requests that it forwards to the sensor class extension.


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