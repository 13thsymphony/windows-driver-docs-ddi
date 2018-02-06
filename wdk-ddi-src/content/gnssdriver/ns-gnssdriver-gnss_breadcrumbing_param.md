---
UID: NS:gnssdriver.GNSS_BREADCRUMBING_PARAM
title: GNSS_BREADCRUMBING_PARAM
author: windows-driver-content
description: This structure contains the configuration passed into the start of breadcrumbing via IOCTL_GNSS_START_BREADCRUMBING.
old-location: sensors\gnss_breadcrumbing_param.htm
old-project: sensors
ms.assetid: 1EAD5B17-B662-4D97-B045-ED09E4AF6E99
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PGNSS_BREADCRUMBING_PARAM structure pointer [Sensor Devices], GNSS_BREADCRUMBING_PARAM, gnssdriver/PGNSS_BREADCRUMBING_PARAM, PGNSS_BREADCRUMBING_PARAM, gnssdriver/GNSS_BREADCRUMBING_PARAM, *PGNSS_BREADCRUMBING_PARAM, sensors.gnss_breadcrumbing_param, GNSS_BREADCRUMBING_PARAM structure [Sensor Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	gnssdriver.h
apiname:
-	GNSS_BREADCRUMBING_PARAM
product: Windows
targetos: Windows
req.typenames: GNSS_BREADCRUMBING_PARAM, *PGNSS_BREADCRUMBING_PARAM
---

# GNSS_BREADCRUMBING_PARAM structure
This structure contains the configuration passed into the start of breadcrumbing via <a href="..\gnssdriver\ni-gnssdriver-ioctl_gnss_start_breadcrumbing.md">IOCTL_GNSS_START_BREADCRUMBING</a>.

## Syntax
````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG MaximumHorizontalUncertainty;
  ULONG MinDistanceBetweenFixes;
  ULONG MaximumErrorTimeoutMs;
  BYTE  Unused[512];
} GNSS_BREADCRUMBING_PARAM, *PGNSS_BREADCRUMBING_PARAM;
````

## Members


`MaximumErrorTimeoutMs`

Contains the maximum error timeout in milliseconds. If the location of the device is unknown for this duration, an error must be recorded in the breadcrumb data. Errors can be recorded earlier if they were already known.

`MaximumHorizontalUncertainty`

Contains the maximum horizontal uncertainty value. Any fix with an error radius larger than this value shall not be recorded.

`MinDistanceBetweenFixes`

Contains the minimum distance between fixes. Only record a fix if the center of it is at least as  far apart as this value from center of the last fix, using a Haversine distance calculation.

`Size`

Structure size.

`Unused`



`Version`

Version number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |