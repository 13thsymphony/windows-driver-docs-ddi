---
UID : NE:sensorsclassextension.MagnetometerAccuracy
title : MagnetometerAccuracy
author : windows-driver-content
description : Specifies the accuracy of the magnetometer.
old-location : sensors\magnetometeraccuracy.htm
old-project : sensors
ms.assetid : DC495EFB-3522-4220-87F8-3DB501831D6E
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : sensorsclassextension/Unknown, sensorsclassextension/Approximate, Approximate, MagnetometerAccuracy, MagnetometerAccuracy enumeration [Sensor Devices], sensorsclassextension/Unreliable, High, sensorsclassextension/MagnetometerAccuracy, sensorsclassextension/High, sensors.magnetometeraccuracy, Unknown, Unreliable
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : sensorsclassextension.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1,Available in Windows 8.1.
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
req.typenames : MagnetometerAccuracy
req.product : Windows 10 or later.
---

# MagnetometerAccuracy Enumeration
Specifies the accuracy of the magnetometer.

## Syntax
````
typedef enum _MagnetometerAccuracy { 
  Unknown      = 0,
  Unreliable   = 1,
  Approximate  = 2,
  High         = 3
} MagnetometerAccuracy;
````

## Constants

<table>

<tr>
<td>MAGNETOMETER_ACCURACY_APPROXIMATE</td>
<td></td>
</tr>

<tr>
<td>MAGNETOMETER_ACCURACY_HIGH</td>
<td></td>
</tr>

<tr>
<td>MAGNETOMETER_ACCURACY_UNKNOWN</td>
<td></td>
</tr>

<tr>
<td>MAGNETOMETER_ACCURACY_UNRELIABLE</td>
<td></td>
</tr>
</table>

## Remarks

Device drivers that support magnetometer accuracy should only report the <b>Unreliable</b>, <b>Approximate</b>, and <b>High</b> values.

Apps that need calibration may periodically ask the user to calibrate the device. We suggest doing this once every 10 minutes.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sensorsclassextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946698">Sensor Properties</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20MagnetometerAccuracy enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>