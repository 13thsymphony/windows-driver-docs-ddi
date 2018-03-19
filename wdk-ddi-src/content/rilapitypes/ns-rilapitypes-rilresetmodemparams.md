---
UID: NS:rilapitypes.RILRESETMODEMPARAMS
title: RILRESETMODEMPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilresetmodemparams.htm
old-project: netvista
ms.assetid: 6fde91f1-375e-4eaa-af48-67099b3e3227
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILRESETMODEMPARAMS, RILRESETMODEMPARAMS, RILRESETMODEMPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilresetmodemparams, ntddrilapitypes/RILRESETMODEMPARAMS"
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
-	RILRESETMODEMPARAMS
product: Windows
targetos: Windows
req.typenames: RILRESETMODEMPARAMS, *LPRILRESETMODEMPARAMS
req.product: Windows 10 or later.
---

# RILRESETMODEMPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILRESETMODEMPARAMS {
  DWORD                       dwResetKind;
  DWORD                       dwNumberOfConfigItems;
  RILRESETMODEMCONFIGITEM [1] rmciModemConfigItems;
} RILRESETMODEMPARAMS, RILRESETMODEMPARAMS;
````

## Members


`dwResetKind`



`dwNumberOfConfigItems`



`rmciModemConfigItems`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |