---
UID : NE:sensorsdef.MAGNETOMETER_ACCURACY
title : MAGNETOMETER_ACCURACY
author : windows-driver-content
description : This enumeration represents the accuracy states of the magnetometer.
old-location : sensors\magnetometer_accuracy.htm
old-project : sensors
ms.assetid : BC8D4FB1-69F4-4FAE-BA90-7CCB57D4A6C4
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : MAGNETOMETER_ACCURACY, MAGNETOMETER_ACCURACY
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : sensorsdef.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : MAGNETOMETER_ACCURACY
req.alt-loc : Sensorsdef.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : MAGNETOMETER_ACCURACY
req.product : Windows 10 or later.
---

# MAGNETOMETER_ACCURACY Enumeration
This enumeration represents the accuracy states of the magnetometer.

## Syntax
````
typedef enum _MAGNETOMETER_ACCURACY { 
  MagnetometerAccuracy_Unknown      = 0,
  MagnetometerAccuracy_Unreliable,
  MagnetometerAccuracy_Approximate,
  MagnetometerAccuracy_High
} MAGNETOMETER_ACCURACY;
````

## Constants

<table>

<tr>
<td>MagnetometerAccuracy_Approximate</td>
<td>Indicates that the magnetometer readings are approximate values.</td>
</tr>

<tr>
<td>MagnetometerAccuracy_High</td>
<td>Indicates that the magnetometer accuracy is set to high.</td>
</tr>

<tr>
<td>MagnetometerAccuracy_Unknown</td>
<td>Indicates that the magnetometer's accuracy cannot be determined.</td>
</tr>

<tr>
<td>MagnetometerAccuracy_Unreliable</td>
<td>Indicates that the magnetometer readings are unreliable. The application can choose to prompt the user to calibrate the compass, to improve accuracy.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sensorsdef.h |