---
UID: NS:rilapitypes.RILSENDFLASHPARAMS
title: RILSENDFLASHPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendflashparams.htm
old-project: netvista
ms.assetid: e45b8f47-4e46-4265-9c56-055e753eb6e6
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILSENDFLASHPARAMS, RILSENDFLASHPARAMS, RILSENDFLASHPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsendflashparams, ntddrilapitypes/RILSENDFLASHPARAMS"
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
-	RILSENDFLASHPARAMS
product: Windows
targetos: Windows
req.typenames: RILSENDFLASHPARAMS, *LPRILSENDFLASHPARAMS
req.product: Windows 10 or later.
---

# RILSENDFLASHPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILSENDFLASHPARAMS {
  DWORD      dwExecutor;
  RILADDRESS raAddress;
} *LPRILSENDFLASHPARAMS, RILSENDFLASHPARAMS;
```

## Members


`dwExecutor`



`raAddress`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |