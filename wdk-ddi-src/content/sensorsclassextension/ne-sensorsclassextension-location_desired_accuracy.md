---
UID : NE:sensorsclassextension.LOCATION_DESIRED_ACCURACY
title : LOCATION_DESIRED_ACCURACY
author : windows-driver-content
description : The LOCATION_DESIRED_ACCURACY enumeration type defines values for the SENSOR_PROPERTY_LOCATION_DESIRED_ACCURACY property.
old-location : sensors\location_desired_accuracy.htm
old-project : sensors
ms.assetid : 21eefb20-b5ad-43c7-a1aa-92731c856363
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : LOCATION_DESIRED_ACCURACY enumeration [Sensor Devices], sensors.location_desired_accuracy, LOCATION_DESIRED_ACCURACY_HIGH, sensorsclassextension/LOCATION_DESIRED_ACCURACY_DEFAULT, Sensor_Enums_a794ec29-a465-4d6a-b32e-c5eb890c95ae.xml, sensorsclassextension/LOCATION_DESIRED_ACCURACY_HIGH, LOCATION_DESIRED_ACCURACY, LOCATION_DESIRED_ACCURACY_DEFAULT, sensorsclassextension/LOCATION_DESIRED_ACCURACY
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : sensorsclassextension.h
req.include-header : 
req.target-type : Windows
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
req.lib : 
req.dll : 
req.irql : "<= PASSIVE_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : LOCATION_DESIRED_ACCURACY
req.product : Windows 10 or later.
---

# LOCATION_DESIRED_ACCURACY Enumeration
The <b>LOCATION_DESIRED_ACCURACY </b>enumeration type defines values for the <a href="https://msdn.microsoft.com/1BF1568D-A889-4158-9C6D-160D9B06F0DE">SENSOR_PROPERTY_LOCATION_DESIRED_ACCURACY</a> property.

## Syntax
````
enum LOCATION_DESIRED_ACCURACY {
  LOCATION_DESIRED_ACCURACY_DEFAULT  = 0, 
  LOCATION_DESIRED_ACCURACY_HIGH     = ( LOCATION_DESIRED_ACCURACY_DEFAULT + 1 ) 

};
````

## Constants

<table>

<tr>
<td>LOCATION_DESIRED_ACCURACY_DEFAULT</td>
<td>Indicates that the sensor should use the accuracy for which it can optimize power and other such cost considerations.</td>
</tr>

<tr>
<td>LOCATION_DESIRED_ACCURACY_HIGH</td>
<td>Indicates that the sensor should deliver the highest-accuracy report possible. This includes using services that might charge money, or consuming higher levels of battery power or connection bandwidth.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sensorsclassextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545610">ISensorDriver::OnGetProperties</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20LOCATION_DESIRED_ACCURACY enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>