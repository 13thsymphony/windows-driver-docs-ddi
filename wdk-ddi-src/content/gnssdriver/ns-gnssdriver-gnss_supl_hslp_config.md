---
UID: NS:gnssdriver.GNSS_SUPL_HSLP_CONFIG
title: GNSS_SUPL_HSLP_CONFIG
author: windows-driver-content
description: This structure contains SUPL H-SLP configuration information.
old-location: sensors\gnss_supl_hslp_config.htm
old-project: sensors
ms.assetid: 08CCC4A8-2D85-436D-B18E-77C91A24F59C
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PGNSS_SUPL_HSLP_CONFIG, GNSS_SUPL_HSLP_CONFIG, GNSS_SUPL_HSLP_CONFIG structure [Sensor Devices], PGNSS_SUPL_HSLP_CONFIG, PGNSS_SUPL_HSLP_CONFIG structure pointer [Sensor Devices], gnssdriver/GNSS_SUPL_HSLP_CONFIG, gnssdriver/PGNSS_SUPL_HSLP_CONFIG, sensors.gnss_supl_hslp_config"
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
-	GNSS_SUPL_HSLP_CONFIG
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_HSLP_CONFIG, *PGNSS_SUPL_HSLP_CONFIG
---

# GNSS_SUPL_HSLP_CONFIG structure
This structure contains SUPL H-SLP configuration information.

## Syntax
````
typedef struct {
  ULONG Size;
  ULONG Version;
  WCHAR SuplHslp[MAX_SERVER_URL_NAME];
  WCHAR SuplHslpFromImsi[MAX_SERVER_URL_NAME];
  ULONG Reserved;
  BYTE  Unused[512];
} GNSS_SUPL_HSLP_CONFIG, *PGNSS_SUPL_HSLP_CONFIG;
````

## Members


`Reserved`

Reserved for future use.

`Size`

Structure size.

`SuplHslp`



`SuplHslpFromImsi`



`Unused`



`Version`

Version number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |