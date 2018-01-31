---
UID : NF:sensorsclassextension.ISensorDriver.OnSetProperties
title : ISensorDriver::OnSetProperties method
author : windows-driver-content
description : The ISensorDriver::OnSetProperties method specifies values for the specified list of properties.
old-location : sensors\isensordriver_onsetproperties.htm
old-project : sensors
ms.assetid : 7c3cca5b-1d08-42dc-8dc4-42eb1160b8bb
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : Sensor_IFaces_1b27ccef-2b50-4942-b8fa-9126e2624b27.xml, ISensorDriver::OnSetProperties, ISensorDriver, OnSetProperties method [Sensor Devices], ISensorDriver interface, sensors.isensordriver_onsetproperties, sensorsclassextension/ISensorDriver::OnSetProperties, ISensorDriver interface [Sensor Devices], OnSetProperties method, OnSetProperties method [Sensor Devices], OnSetProperties
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


# OnSetProperties method
The <b>ISensorDriver::OnSetProperties</b> method specifies values for the specified list of properties.

## Syntax

````
HRESULT OnSetProperties(
  [in]  IWDFFile              *pClientFile,
  [in]  LPWSTR                pwszSensorID,
  [in]  IPortableDeviceValues *pPropertiesToSet,
  [out] IPortableDeviceValues **ppResults
);
````

## Parameters

`pClientFile`

Pointer to an <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface that represents the file object for the application specifying property values.

`pwszSensorID`

<b>LPWSTR</b> that contains the ID for the sensor for which the client application is specifying property values.

`pPropertiesToSet`

Pointer to an <a href="http://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> interface that contains the list of properties to set and their values.

`ppResults`

Address of an <a href="http://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> pointer that receives the list of properties that have been set successfully and their new values. If a property was not set, the new value contains an HRESULT error code.


## Return Value

If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## Remarks

Properties describe the sensor device, as opposed to data fields, which contain sensor-generated data.  Platform-defined properties are defined in sensors.h.

The list of properties provided through <i>pPropertiesToSet</i> is typically  a subset of the list you returned through <a href="https://msdn.microsoft.com/library/windows/hardware/ff545630">ISensorDriver::OnGetSupportedProperties</a>. However, the sensor class extension does not enforce this condition on client applications.

The sensor class extension is responsible for freeing any <b>PROPVARIANT</b> structures returned by this method.

<a href="http://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> is documented in Windows Portable Devices.
<div class="alert"><b>Note</b>  This method will be called only if the user has enabled the sensor in the <b>Location and Other Sensors</b> control panel.</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sensorsclassextension.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545610">ISensorDriver::OnGetProperties</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20ISensorDriver::OnSetProperties method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>