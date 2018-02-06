---
UID: NF:sensorsclassextension.ISensorClassExtension.Initialize
title: ISensorClassExtension::Initialize method
author: windows-driver-content
description: The ISensorClassExtension::Initialize method initializes the sensor class extension object.
old-location: sensors\isensorclassextension_initialize.htm
old-project: sensors
ms.assetid: 9b5b9cdf-06a9-410f-87c3-b87318c25a11
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: sensors.isensorclassextension_initialize, Initialize method [Sensor Devices], ISensorClassExtension, Initialize, ISensorClassExtension::Initialize
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
-	Initialize
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---


# Initialize method
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545514">ISensorClassExtension::Initialize</a> method initializes the sensor class extension object.

## Syntax

````
HRESULT Initialize(
   IUnknown * pWdfDeviceUnknown,
   IUnknown * pSensorDriverUnknown
);
````

## Parameters

`pWdfDeviceUnknown`

IUnknown pointer for the driver class that implements the IWDFDevice interface.

`pSensorDriverUnknown`

IUnknown pointer for the object that implements the ISensorDriver callback interface.


## Return Value

This method returns an HRESULT. Possible values include, but are not limited to, one of the following values. See Remarks.
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
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
The argument was <b>NULL</b> or the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface is missing..

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_ALREADY_EXISTS)</b></dt>
</dl>
</td>
<td width="60%">
The class extension is already initialized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_ALREADY_INITIALIZED)</b></dt>
</dl>
</td>
<td width="60%">
The class extension is already initialized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_FOUND)</b></dt>
</dl>
</td>
<td width="60%">
The WPD_OBJECT_ID for the sensor is not valid.

</td>
</tr>
</table>

## Remarks

First, create the sensor class extension by calling the COM CoCreateInstance method, and then call Initialize. We recommend that you perform these initialization steps when called by UMDF in <a href="https://msdn.microsoft.com/library/windows/hardware/ff556766">IPnpCallbackHardware::OnPrepareHardware</a>. After Initialize returns, the driver must be ready to receive callbacks from the sensor class extension. The sensor class extension calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545633">ISensorDriver::OnGetSupportedSensorObjects</a> during initialization. Your driver must be ready to return values for all required properties and data fields before it calls Initialize.

Because the class extension calls your driver during initialization, this method can also return HRESULTs that your driver returns from <a href="https://msdn.microsoft.com/library/windows/hardware/ff545633">ISensorDriver::OnGetSupportedSensorObjects</a>.
<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | sensorsclassextension.h |
| **Library** | SensorsClassExtension.lib |