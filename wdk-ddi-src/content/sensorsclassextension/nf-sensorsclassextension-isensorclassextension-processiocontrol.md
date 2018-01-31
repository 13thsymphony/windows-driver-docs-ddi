---
UID : NF:sensorsclassextension.ISensorClassExtension.ProcessIoControl
title : ISensorClassExtension::ProcessIoControl method
author : windows-driver-content
description : The ISensorClassExtension::ProcessControl method sends Windows Portable Devices (WPD) I/O control requests to the sensor class extension for processing.
old-location : sensors\isensorclassextension_processiocontrol.htm
old-project : sensors
ms.assetid : bd886086-4e23-47c0-ae58-9234399e5a79
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : sensors.isensorclassextension_processiocontrol, ISensorClassExtension::ProcessIoControl, ProcessIoControl method [Sensor Devices], ISensorClassExtension, ProcessIoControl
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


# ProcessIoControl method
The <a href="https://msdn.microsoft.com/bd886086-4e23-47c0-ae58-9234399e5a79">ISensorClassExtension::ProcessControl</a> method sends Windows Portable Devices (WPD) I/O control requests to the sensor class extension for processing.

## Syntax

````
HRESULT ProcessIoControl(
   IWDFIoRequest * pRequest
);
````

## Parameters

`pRequest`

Pointer to the IWDFIoRequest interface that represents the UMDF request object.


## Return Value

This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
No permission. For example, the I/O request sought data for which no permission exists.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
A required pointer argument was <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_SUPPORTED)</b></dt>
</dl>
</td>
<td width="60%">
The request did not contain a WPD IOCTL.

</td>
</tr>
</table>

## Remarks

UMDF sends I/O control requests to sensor drivers through <a href="https://msdn.microsoft.com/library/windows/hardware/ff556854">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a>. We recommend that you call ProcessIoControl to forward all WPD requests to the sensor class extension for processing. You can use the WPD macro IS_WPD_IOCTL to determine whether a given control code is specific to WPD. Clients of the Sensor API and Location API send only WPD IOCTLs, which can always be process by the sensor class extension.

After processing an I/O control request, the sensor class extension uses the driver's callback interface, <a href="..\sensorsclassextension\nn-sensorsclassextension-isensordriver.md">ISensorDriver</a>, to provide notifications, as appropriate. WPD requests that the sensor class extension does not handle by default are sent to the driver through <a href="https://msdn.microsoft.com/library/windows/hardware/ff545644">ISensorDriver::OnProcessWpdMessage</a>.

The driver must not complete I/O control requests that it forwards to the sensor class extension.

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