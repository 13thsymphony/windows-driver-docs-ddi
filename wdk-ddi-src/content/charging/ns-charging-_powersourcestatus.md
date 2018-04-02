---
UID: NS:charging._POWERSOURCESTATUS
title: "_POWERSOURCESTATUS"
author: windows-driver-content
description: This struct is for internal use only.
old-location: battery\powersourcestatus.htm
old-project: battery
ms.assetid: 9386DBEC-A47D-44A5-8AF8-D5B406143070
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PPOWERSOURCESTATUS, POWERSOURCESTATUS, POWERSOURCESTATUS structure [Battery Devices], _POWERSOURCESTATUS, battery.powersourcestatus, charging/BATTERY_INFORMATION"
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
product:
- Windows
targetos: Windows
req.typenames: POWERSOURCESTATUS, *PPOWERSOURCESTATUS
---

# _POWERSOURCESTATUS structure
This struct is for internal use only.

## Syntax
```
typedef struct _POWERSOURCESTATUS {
  POWERSOURCEID PowerSourceId;
  ULONG         MaxChargeCurrent;
  ULONG         PowerSourceInformation;
  BOOLEAN       PowerSourceStatus;
} POWERSOURCESTATUS, *PPOWERSOURCESTATUS;
```

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | charging.h (include Charging.h) |