---
UID : NS:gnssdriver.GNSS_SATELLITEINFO
title : GNSS_SATELLITEINFO
author : windows-driver-content
description : This structure defines satellite-related information of a fix.
old-location : sensors\gnss_satelliteinfo.htm
old-project : sensors
ms.assetid : 27F537D8-45B2-43D9-A614-3558534C9DBA
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : PGNSS_SATELLITEINFO structure pointer [Sensor Devices], GNSS_SATELLITEINFO structure [Sensor Devices], sensors.gnss_satelliteinfo, GNSS_SATELLITEINFO, PGNSS_SATELLITEINFO, *PGNSS_SATELLITEINFO, gnssdriver/GNSS_SATELLITEINFO, gnssdriver/PGNSS_SATELLITEINFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PGNSS_SATELLITEINFO, GNSS_SATELLITEINFO"
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


`Azimuth`

Azimuth value.

`Elevation`

Elevation value

`SatelliteId`

Pseudorandom noise (PRN) code or other identification for the satellite.

`SignalToNoiseRatio`

Signal to noise ratio.

`UsedInPositiong`

Indicates whether this was simply a visible satellite or actually used in the positioning.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | gnssdriver.h |