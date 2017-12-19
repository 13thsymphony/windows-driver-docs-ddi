---
UID: NS.SENSORSDEF.SENSOR_VALUE_PAIR
title: SENSOR_VALUE_PAIR
author: windows-driver-content
description: This structure pairs the property keys listed in the Sensor properties section with the data that each key represents.
old-location: sensors\sensor_value_pair.htm
old-project: sensors
ms.assetid: 0D0B06FE-BE88-4FB2-92FC-8B6D396CEFE8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SENSOR_VALUE_PAIR, PSENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sensorsdef.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SENSOR_VALUE_PAIR
req.alt-loc: Sensorsdef.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# SENSOR_VALUE_PAIR structure



## -description
This structure pairs the property keys listed in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn946698">Sensor properties</a> section with the data that each key represents.



## -syntax

````
typedef struct _SENSOR_VALUE_PAIR {
  PROPERTYKEY Key;
  PROPVARIANT Value;
} SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR;
````


## -struct-fields

### -field Key

A property key that is associated with a sensor. For a list of the valid property keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn946698">Sensor properties</a>.


### -field Value

A value that is associated with the property key element.


## -remarks
The Value is one of the VT types (VARTYPE) that are supported by the sensor class extension (CX):


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
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Sensorsdef.h</dt>
</dl>
</td>
</tr>
</table>