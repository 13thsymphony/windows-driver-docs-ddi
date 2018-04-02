---
UID: NS:gnssdriver.GNSS_BREADCRUMB_V1
title: GNSS_BREADCRUMB_V1
author: windows-driver-content
description: This structure contains an individual breadcrumb. The order and types of the fields are designed to pack densely.
old-location: sensors\gnss_breadcrumb_v1.htm
old-project: sensors
ms.assetid: BE1D09C4-8EC0-4BF3-A943-20EDD44F9CF1
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PGNSS_BREADCRUMB_V1, GNSS_BREADCRUMB_V1, GNSS_BREADCRUMB_V1 structure [Sensor Devices], PGNSS_BREADCRUMB_V1, PGNSS_BREADCRUMB_V1 structure pointer [Sensor Devices], gnssdriver/GNSS_BREADCRUMB_V1, gnssdriver/PGNSS_BREADCRUMB_V1, sensors.gnss_breadcrumb_v1"
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
-	GNSS_BREADCRUMB_V1
product:
- Windows
targetos: Windows
req.typenames: GNSS_BREADCRUMB_V1, *PGNSS_BREADCRUMB_V1
---

# GNSS_BREADCRUMB_V1 structure
This structure contains an individual breadcrumb. The order and types of the fields are designed  to pack densely.

## Syntax
```
typedef struct GNSS_BREADCRUMB_V1 {
  FILETIME       FixTimeStamp;
  double         Latitude;
  double         Longitude;
  ULONG          HorizontalAccuracy;
  unsigned short Speed;
  unsigned short SpeedAccuracy;
  short          Altitude;
  unsigned short AltitudeAccuracy;
  short          Heading;
  unsigned char  HeadingAccuracy;
  unsigned char  FixSuccess;
}  *PGNSS_BREADCRUMB_V1;
```

## Members


`FixTimeStamp`

Contains the breadcrumb fix timestamp value.

`Latitude`

Contains the breadcrumb longitude value at the time of the fix.

`Longitude`

Contains the breadcrumb latitude at the time of the fix.

`HorizontalAccuracy`

Contains the breadcrumb horizontal altitude value.

`Speed`

Contains the speed value at the time of the breadcrumb fix.

`SpeedAccuracy`

Contains the breadcrumb speed accuracy value.

`Altitude`

Contains the breadcrumb altitude value at the time of the fix.

`AltitudeAccuracy`

Contains the breadcrumb altitude accuracy value.

`Heading`

Contains the breadcrumb heading value at the time of the fix.

`HeadingAccuracy`

Contains the breadcrumb heading accuracy value.

`FixSuccess`

A Boolean type that contains the fix success value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |