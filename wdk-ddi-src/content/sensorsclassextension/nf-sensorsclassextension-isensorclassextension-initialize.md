---
UID: NF.sensorsclassextension.ISensorClassExtension.Initialize
title: ISensorClassExtension::Initialize method
author: windows-driver-content
description: The ISensorClassExtension::Initialize method initializes the sensor class extension object.
old-location: sensors\isensorclassextension_initialize.htm
old-project: sensors
ms.assetid: 9b5b9cdf-06a9-410f-87c3-b87318c25a11
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISensorClassExtension, ISensorClassExtension::Initialize, Initialize
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
req.alt-api: Initialize
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

# ISensorClassExtension::Initialize method



## -description
The <a href="sensors.isensorclassextension_initialize">ISensorClassExtension::Initialize</a> method initializes the sensor class extension object.



## -syntax

````
HRESULT Initialize(
   IUnknown * pWdfDeviceUnknown,
   IUnknown * pSensorDriverUnknown
);
````


## -parameters

### -param pWdfDeviceUnknown 

IUnknown pointer for the driver class that implements the IWDFDevice interface.


### -param pSensorDriverUnknown 

IUnknown pointer for the object that implements the ISensorDriver callback interface.


## -returns
This method returns an HRESULT. Possible values include, but are not limited to, one of the following values. See Remarks.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method succeeded.
<dl>
<dt><b>E_POINTER</b></dt>
</dl>The argument was <b>NULL</b> or the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface is missing..
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_ALREADY_EXISTS)</b></dt>
</dl>The class extension is already initialized.
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_ALREADY_INITIALIZED)</b></dt>
</dl>The class extension is already initialized.
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_FOUND)</b></dt>
</dl>The WPD_OBJECT_ID for the sensor is not valid.

 


## -remarks
First, create the sensor class extension by calling the COM CoCreateInstance method, and then call Initialize. We recommend that you perform these initialization steps when called by UMDF in <a href="umdf.ipnpcallbackhardware_onpreparehardware">IPnpCallbackHardware::OnPrepareHardware</a>. After Initialize returns, the driver must be ready to receive callbacks from the sensor class extension. The sensor class extension calls <a href="sensors.isensordriver_ongetsupportedsensorobjects">ISensorDriver::OnGetSupportedSensorObjects</a> during initialization. Your driver must be ready to return values for all required properties and data fields before it calls Initialize.

Because the class extension calls your driver during initialization, this method can also return HRESULTs that your driver returns from <a href="sensors.isensordriver_ongetsupportedsensorobjects">ISensorDriver::OnGetSupportedSensorObjects</a>.


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