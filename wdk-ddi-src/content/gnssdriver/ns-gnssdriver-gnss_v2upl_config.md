---
UID: NS:gnssdriver.GNSS_V2UPL_CONFIG
title: GNSS_V2UPL_CONFIG
author: windows-driver-content
description: This structure contains V2UPL configuration information.
old-location: sensors\gnss_v2upl_config.htm
old-project: sensors
ms.assetid: A1DCC547-8CAA-46B9-A855-5F591C69A3B0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_V2UPL_CONFIG structure [Sensor Devices], *PGNSS_V2UPL_CONFIG, PGNSS_V2UPL_CONFIG structure pointer [Sensor Devices], PGNSS_V2UPL_CONFIG, gnssdriver/PGNSS_V2UPL_CONFIG, sensors.gnss_v2upl_config, GNSS_V2UPL_CONFIG, gnssdriver/GNSS_V2UPL_CONFIG
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
-	GNSS_V2UPL_CONFIG
product: Windows
targetos: Windows
req.typenames: GNSS_V2UPL_CONFIG, *PGNSS_V2UPL_CONFIG
---

# GNSS_V2UPL_CONFIG structure
This structure contains V2UPL configuration information.

## Syntax
````
typedef struct {
  ULONG Size;
  ULONG Version;
  CHAR  MPC[MAX_SERVER_URL_NAME];
  CHAR  PDE[MAX_SERVER_URL_NAME];
  BYTE  ApplicationTypeIndicator_MR;
} GNSS_V2UPL_CONFIG, *PGNSS_V2UPL_CONFIG;
````

## Members


`ApplicationTypeIndicator_MR`

Application type indicator for any mobile originated location request to the MPC. It shall be set to the value for Microsoft resident applications based on intelligent platform.

`MPC`



`PDE`



`Size`

Structure size.

`Unused`



`Version`

Version number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |