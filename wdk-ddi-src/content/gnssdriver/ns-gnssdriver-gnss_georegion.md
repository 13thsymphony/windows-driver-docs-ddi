---
UID: NS:gnssdriver.GNSS_GEOREGION
title: GNSS_GEOREGION
author: windows-driver-content
description: This structure defines the geographical shape of a geofence.
old-location: sensors\gnss_georegion.htm
old-project: sensors
ms.assetid: 70FC3BCE-3869-4263-8870-BB97438CB5F1
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PGNSS_GEOREGION, GNSS_GEOREGION, GNSS_GEOREGION structure [Sensor Devices], PGNSS_GEOREGION, PGNSS_GEOREGION structure pointer [Sensor Devices], gnssdriver/GNSS_GEOREGION, gnssdriver/PGNSS_GEOREGION, sensors.gnss_georegion"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	GNSS_GEOREGION
product: Windows
targetos: Windows
req.typenames: GNSS_GEOREGION, *PGNSS_GEOREGION
---

# GNSS_GEOREGION structure
This structure defines the geographical shape of  a geofence.

## Syntax
````
typedef struct {
  ULONG              Size;
  ULONG              Version;
  GNSS_GEOREGIONTYPE GeoRegionType;
  union {
    GNSS_GEOREGION_CIRCLE Circle;
    BYTE                  Unused[512];
  };
} GNSS_GEOREGION, *PGNSS_GEOREGION;
````

## Members


`GeoRegionType`

<a href="..\gnssdriver\ne-gnssdriver-gnss_georegiontype.md">GNSS_GEOREGIONTYP</a>E enumeration that defines the georegion type of a geofence.

`Size`

Structure size.

`Version`

Version number.

## Remarks
A geographical shape is used to define a geofence.  Windows 10 currently supports only circular geofences.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |