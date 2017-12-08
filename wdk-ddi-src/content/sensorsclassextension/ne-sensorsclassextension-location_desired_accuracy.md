---
UID: NE.sensorsclassextension.LOCATION_DESIRED_ACCURACY
title: LOCATION_DESIRED_ACCURACY
author: windows-driver-content
description: The LOCATION_DESIRED_ACCURACY enumeration type defines values for the SENSOR_PROPERTY_LOCATION_DESIRED_ACCURACY property.
old-location: sensors\location_desired_accuracy.htm
old-project: sensors
ms.assetid: 21eefb20-b5ad-43c7-a1aa-92731c856363
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: LOCATION_DESIRED_ACCURACY, LOCATION_DESIRED_ACCURACY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 7,Available in Windows 7.
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: LOCATION_DESIRED_ACCURACY
req.alt-loc: SensorsClassExtension.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# LOCATION_DESIRED_ACCURACY enumeration



## -description
The <b>LOCATION_DESIRED_ACCURACY </b>enumeration type defines values for the <a href="https://msdn.microsoft.com/a9f88dad-a81d-45dc-b607-e7b4c5036774">SENSOR_PROPERTY_LOCATION_DESIRED_ACCURACY</a> property.


## -syntax

````
enum LOCATION_DESIRED_ACCURACY {
  LOCATION_DESIRED_ACCURACY_DEFAULT  = 0, 
  LOCATION_DESIRED_ACCURACY_HIGH     = ( LOCATION_DESIRED_ACCURACY_DEFAULT + 1 ) 

};
````


## -enum-fields

### -field LOCATION_DESIRED_ACCURACY_DEFAULT

Indicates that the sensor should use the accuracy for which it can optimize power and other such cost considerations.

### -field LOCATION_DESIRED_ACCURACY_HIGH

Indicates that the sensor should deliver the highest-accuracy report possible. This includes using services that might charge money, or consuming higher levels of battery power or connection bandwidth.

## -remarks


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
<dt>SensorsClassExtension.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="sensors.isensordriver_ongetproperties">ISensorDriver::OnGetProperties</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20LOCATION_DESIRED_ACCURACY enumeration%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
