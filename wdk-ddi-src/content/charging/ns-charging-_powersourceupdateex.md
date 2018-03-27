---
UID: NS:charging._POWERSOURCEUPDATEEX
title: "_POWERSOURCEUPDATEEX"
author: windows-driver-content
description: This structure is for internal use only.
old-location: battery\powersourceupdateex.htm
old-project: battery
ms.assetid: FAA39A82-E27E-41BD-9830-03EAE7CFF64F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX structure [Battery Devices], _POWERSOURCEUPDATEEX, battery.powersourceupdateex, charging/BATTERY_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: charging.h
req.include-header: Charging.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Charging.h
api_name:
-	BATTERY_INFORMATION
product: Windows
targetos: Windows
req.typenames: POWERSOURCEUPDATEEX, *PPOWERSOURCEUPDATEEX
---

# _POWERSOURCEUPDATEEX structure
This structure is for internal use only.

## Syntax
```
typedef struct _POWERSOURCEUPDATEEX {
  POWERSOURCEUPDATE Source;
  GUID              ChargerId;
} POWERSOURCEUPDATEEX, *PPOWERSOURCEUPDATEEX;
```

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | charging.h (include Charging.h) |