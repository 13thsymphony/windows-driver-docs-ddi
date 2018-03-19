---
UID: NS:gnssdriver.GNSS_SATELLITEINFO
title: GNSS_SATELLITEINFO
author: windows-driver-content
description: This structure defines satellite-related information of a fix.
old-location: gnss\gnss_satelliteinfo.htm
old-project: gnss
ms.assetid: 27F537D8-45B2-43D9-A614-3558534C9DBA
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGNSS_SATELLITEINFO, GNSS_SATELLITEINFO, GNSS_SATELLITEINFO structure [Sensor Devices], PGNSS_SATELLITEINFO, PGNSS_SATELLITEINFO structure pointer [Sensor Devices], gnss.gnss_satelliteinfo, gnssdriver/GNSS_SATELLITEINFO, gnssdriver/PGNSS_SATELLITEINFO"
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
-	GNSS_SATELLITEINFO
product: Windows
targetos: Windows
req.typenames: GNSS_SATELLITEINFO, *PGNSS_SATELLITEINFO
---

# GNSS_SATELLITEINFO structure
This structure defines satellite-related information of a fix.

## Syntax
````
typedef struct {
  ULONG  SatelliteId;
  BOOL   UsedInPositiong;
  double Elevation;
  double Azimuth;
  double SignalToNoiseRatio;
} GNSS_SATELLITEINFO, *PGNSS_SATELLITEINFO;
````

## Members


`SatelliteId`

Pseudorandom noise (PRN) code or other identification for the satellite.

`UsedInPositiong`

Indicates whether this was simply a visible satellite or actually used in the positioning.

`Elevation`

Elevation value

`Azimuth`

Azimuth value.

`SignalToNoiseRatio`

Signal to noise ratio.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |