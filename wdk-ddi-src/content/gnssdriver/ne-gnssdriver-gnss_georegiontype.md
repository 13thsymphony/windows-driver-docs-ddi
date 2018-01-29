---
UID : NE:gnssdriver.GNSS_GEOREGIONTYPE
title : GNSS_GEOREGIONTYPE
author : windows-driver-content
description : This enumeration is used for defining a geographical shape. A shape is used to define a geofence. Windows 10 currently only supports circular geofences.
old-location : sensors\gnss_georegiontype.htm
old-project : sensors
ms.assetid : 736A1D63-A96E-4E29-ADFD-F441AC4757C6
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : gnssdriver/GNSS_GeoRegion_Circle, sensors.gnss_georegiontype, GNSS_GEOREGIONTYPE, GNSS_GeoRegion_Circle, gnssdriver/GNSS_GEOREGIONTYPE, GNSS_GEOREGIONTYPE enumeration [Sensor Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : gnssdriver.h
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
req.lib : 
req.dll : 
req.irql : <= DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : GNSS_GEOREGIONTYPE
---

# GNSS_GEOREGIONTYPE Enumeration
This enumeration is used for defining a geographical shape. A shape is used to define a geofence. Windows 10 currently only supports circular geofences.

## Syntax
````
typedef enum  { 
  GNSS_GeoRegion_Circle  = 0x01
} GNSS_GEOREGIONTYPE;
````

## Constants

<table>

<tr>
<td>GNSS_GeoRegion_Circle</td>
<td>Defines a circular geofence.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | gnssdriver.h |