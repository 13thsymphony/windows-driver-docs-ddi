---
UID: NS:gnssdriver.GNSS_STOPFIXSESSION_PARAM
title: GNSS_STOPFIXSESSION_PARAM
author: windows-driver-content
description: This structure is used to stop an active fix session.
old-location: sensors\gnss_stopfixsession_param.htm
old-project: sensors
ms.assetid: 37D56DC0-C35B-4651-93E9-28AF76041D5D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: gnssdriver/PGNSS_STOPFIXSESSION_PARAM, GNSS_STOPFIXSESSION_PARAM, *PGNSS_STOPFIXSESSION_PARAM, sensors.gnss_stopfixsession_param, PGNSS_STOPFIXSESSION_PARAM structure pointer [Sensor Devices], PGNSS_STOPFIXSESSION_PARAM, gnssdriver/GNSS_STOPFIXSESSION_PARAM, GNSS_STOPFIXSESSION_PARAM structure [Sensor Devices]
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
-	GNSS_STOPFIXSESSION_PARAM
product: Windows
targetos: Windows
req.typenames: "*PGNSS_STOPFIXSESSION_PARAM, GNSS_STOPFIXSESSION_PARAM"
---

# GNSS_STOPFIXSESSION_PARAM structure
This structure is used to stop an active fix session.

## Syntax
````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG FixSessionID;
  BYTE  Unused[512];
} GNSS_STOPFIXSESSION_PARAM, *PGNSS_STOPFIXSESSION_PARAM;
````

## Members


`FixSessionID`

ID of an active fix session.

`Size`

Structure size.

`Unused`



`Version`

Version number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |