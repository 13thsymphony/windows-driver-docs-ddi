---
UID: NE.sensorsclassextension.MagnetometerAccuracy
title: MagnetometerAccuracy
author: windows-driver-content
description: Specifies the accuracy of the magnetometer.
old-location: sensors\magnetometeraccuracy.htm
old-project: sensors
ms.assetid: DC495EFB-3522-4220-87F8-3DB501831D6E
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: MagnetometerAccuracy, MagnetometerAccuracy
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,Available in Windows 8.1.
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MagnetometerAccuracy
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

# MagnetometerAccuracy enumeration



## -description
Specifies the accuracy of the magnetometer.



## -syntax

````
typedef enum _MagnetometerAccuracy { 
  Unknown      = 0,
  Unreliable   = 1,
  Approximate  = 2,
  High         = 3
} MagnetometerAccuracy;
````


## -enum-fields

### -field Unknown

The accuracy is currently not available, typically because the driver can't report it.


### -field Unreliable

The reported values have a high degree of inaccuracy. Apps should always ask the user to calibrate the device whenever this value is returned.


### -field Approximate

          The actual and reported values differ but may be accurate enough for some applications. Apps that only need a relative value, like a virtual reality app, can continue without additional calibration.


### -field High

          The actual and reported values are accurate. No additional calibration is needed.


## -remarks
Device drivers that support magnetometer accuracy should only report the <b>Unreliable</b>, <b>Approximate</b>, and <b>High</b> values.

Apps that need calibration may periodically ask the user to calibrate the device. We suggest doing this once every 10 minutes.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

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
Available in Windows 8.1.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946698">Sensor Properties</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20MagnetometerAccuracy enumeration%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

