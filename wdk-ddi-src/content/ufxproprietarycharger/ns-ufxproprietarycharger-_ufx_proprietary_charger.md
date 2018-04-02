---
UID: NS:ufxproprietarycharger._UFX_PROPRIETARY_CHARGER
title: "_UFX_PROPRIETARY_CHARGER"
author: windows-driver-content
description: Describes the proprietary charger's device power requirements.
old-location: buses\ufx_proprietary_charger.htm
old-project: usbref
ms.assetid: FAAEDAFE-69A8-4092-8301-DB159FD3583D
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUFX_PROPRIETARY_CHARGER, PUFX_PROPRIETARY_CHARGER, PUFX_PROPRIETARY_CHARGER structure pointer [Buses], UFX_PROPRIETARY_CHARGER, UFX_PROPRIETARY_CHARGER structure [Buses], _UFX_PROPRIETARY_CHARGER, buses.ufx_proprietary_charger, ufxproprietarycharger/PUFX_PROPRIETARY_CHARGER, ufxproprietarycharger/UFX_PROPRIETARY_CHARGER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ufxproprietarycharger.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ufxproprietarycharger.h
api_name:
-	UFX_PROPRIETARY_CHARGER
product:
- Windows
targetos: Windows
req.typenames: UFX_PROPRIETARY_CHARGER, *PUFX_PROPRIETARY_CHARGER
req.product: Windows 10 or later.
---

# _UFX_PROPRIETARY_CHARGER structure
Describes the proprietary charger's device power requirements.

## Syntax
```
typedef struct _UFX_PROPRIETARY_CHARGER {
  GUID               ChargerId;
  DEVICE_POWER_STATE DxState;
} UFX_PROPRIETARY_CHARGER, *PUFX_PROPRIETARY_CHARGER;
```

## Members


`ChargerId`

Charger identifier used to identify a specific type of charger.

`DxState`

The minimum required device power state when it is connected, indicated by one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554628">DEVICE_POWER_STATE</a>-typed flags.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ufxproprietarycharger.h |