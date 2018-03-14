---
UID: NS:rilapitypes.RILEMERGENCYMODECONTROLPARAMS
title: RILEMERGENCYMODECONTROLPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencymodecontrolparams.htm
old-project: netvista
ms.assetid: b25ecc96-1ed2-4d8f-8dc8-0fafe58eca24
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILEMERGENCYMODECONTROLPARAMS, RILEMERGENCYMODECONTROLPARAMS, RILEMERGENCYMODECONTROLPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilemergencymodecontrolparams, ntddrilapitypes/RILEMERGENCYMODECONTROLPARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILEMERGENCYMODECONTROLPARAMS
product: Windows
targetos: Windows
req.typenames: RILEMERGENCYMODECONTROLPARAMS, *LPRILEMERGENCYMODECONTROLPARAMS
req.product: Windows 10 or later.
---

# RILEMERGENCYMODECONTROLPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILEMERGENCYMODECONTROLPARAMS {
  DWORD                                 dwExecutor;
  RILEMERGENCYMODECONTROLPARAMSCONTROL  dwEmergencyModeControl;
} RILEMERGENCYMODECONTROLPARAMS, RILEMERGENCYMODECONTROLPARAMS;
````

## Members


`dwEmergencyModeControl`



`dwExecutor`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |