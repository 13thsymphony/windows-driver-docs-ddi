---
UID: NS:gnssdriver.GNSS_V2UPL_CONFIG
title: GNSS_V2UPL_CONFIG
author: windows-driver-content
description: This structure contains V2UPL configuration information.
old-location: gnss\gnss_v2upl_config.htm
old-project: gnss
ms.assetid: A1DCC547-8CAA-46B9-A855-5F591C69A3B0
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGNSS_V2UPL_CONFIG, GNSS_V2UPL_CONFIG, GNSS_V2UPL_CONFIG structure [Sensor Devices], PGNSS_V2UPL_CONFIG, PGNSS_V2UPL_CONFIG structure pointer [Sensor Devices], gnss.gnss_v2upl_config, gnssdriver/GNSS_V2UPL_CONFIG, gnssdriver/PGNSS_V2UPL_CONFIG"
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


`Size`

Structure size.

`Version`

Version number.

`MPC`



`PDE`



`ApplicationTypeIndicator_MR`

Application type indicator for any mobile originated location request to the MPC. It shall be set to the value for Microsoft resident applications based on intelligent platform.

`Unused`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |