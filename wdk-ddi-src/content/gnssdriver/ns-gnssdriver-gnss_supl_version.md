---
UID: NS:gnssdriver.GNSS_SUPL_VERSION
title: GNSS_SUPL_VERSION
author: windows-driver-content
description: This structure contains SUPL version information.
old-location: sensors\gnss_supl_version.htm
old-project: sensors
ms.assetid: D004DAEF-F25F-442D-9A6D-91FB8A18E0DB
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PGNSS_SUPL_VERSION, GNSS_SUPL_VERSION, GNSS_SUPL_VERSION structure [Sensor Devices], PGNSS_SUPL_VERSION, PGNSS_SUPL_VERSION structure pointer [Sensor Devices], gnssdriver/GNSS_SUPL_VERSION, gnssdriver/PGNSS_SUPL_VERSION, sensors.gnss_supl_version"
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
-	GNSS_SUPL_VERSION
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_VERSION, *PGNSS_SUPL_VERSION
---

# GNSS_SUPL_VERSION structure
This structure contains SUPL version information.

## Syntax
```
typedef struct GNSS_SUPL_VERSION {
  ULONG MajorVersion;
  ULONG MinorVersion;
}  *PGNSS_SUPL_VERSION;
```

## Members


`MajorVersion`

Major version number.

`MinorVersion`

Minor version number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |