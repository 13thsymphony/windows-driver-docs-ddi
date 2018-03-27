---
UID: NS:charging._CHARGINGSTATUSCOMPLETE
title: "_CHARGINGSTATUSCOMPLETE"
author: windows-driver-content
description: This structure is for internal use only.
old-location: battery\chargingstatuscomplete.htm
old-project: battery
ms.assetid: 5B5BD82A-15A3-40AA-9FE8-191B31CB694A
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCHARGINGSTATUSCOMPLETE, CHARGINGSTATUSCOMPLETE, CHARGINGSTATUSCOMPLETE structure [Battery Devices], _CHARGINGSTATUSCOMPLETE, battery.chargingstatuscomplete, charging/BATTERY_INFORMATION"
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
req.typenames: CHARGINGSTATUSCOMPLETE, *PCHARGINGSTATUSCOMPLETE
---

# _CHARGINGSTATUSCOMPLETE structure
This structure is for internal use only.

## Syntax
```
typedef struct _CHARGINGSTATUSCOMPLETE {
  POWERSOURCESTATUS UsbFnStatus;
  POWERSOURCESTATUS UsbTypeCStatus;
  POWERSOURCESTATUS KDStatus;
  POWERSOURCESTATUS WirelessStatus;
  ULONG             ForceDisableChargingRefCount;
} *PCHARGINGSTATUSCOMPLETE, CHARGINGSTATUSCOMPLETE;
```

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | charging.h (include Charging.h) |