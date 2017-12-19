---
UID: NS.GNSSDRIVER.GNSS_GEOREGION_CIRCLE
title: GNSS_GEOREGION_CIRCLE
author: windows-driver-content
description: This structure is used for defining a circular geofence.
old-location: sensors\gnss_georegion_circle.htm
old-project: sensors
ms.assetid: 498F8325-C887-4FDE-8BCF-A713639E3B35
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_GEOREGION_CIRCLE, GNSS_GEOREGION_CIRCLE, *PGNSS_GEOREGION_CIRCLE, PGNSS_GEOREGION_CIRCLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_GEOREGION_CIRCLE
req.alt-loc: gnssdriver.h
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
---

# GNSS_GEOREGION_CIRCLE structure



## -description
This structure is used for defining a circular geofence.



## -syntax

````
typedef struct {
  double Latitude;
  double Longitude;
  double RadiusInMeters;
} GNSS_GEOREGION_CIRCLE, *PGNSS_GEOREGION_CIRCLE;
````


## -struct-fields

### -field Latitude

Latitude of the center of the circle.


### -field Longitude

Longitude of the center of the circle.


### -field RadiusInMeters

Radius of the circle in meters.


## -remarks
A geographical shape is used to define a geofence.  Windows 10 currently supports only circular geofences.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>