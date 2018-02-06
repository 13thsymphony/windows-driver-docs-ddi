---
UID: NS:rilapitypes.RILSENDFLASHPARAMS
title: RILSENDFLASHPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendflashparams_2.htm
old-project: netvista
ms.assetid: 2279c1f2-382f-4cae-a881-997f0bed7b6d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilsendflashparams_2, rilapitypes/RILSENDFLASHPARAMS, RILSENDFLASHPARAMS structure [Network Drivers Starting with Windows Vista], RILSENDFLASHPARAMS, *LPRILSENDFLASHPARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
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
-	rilapitypes.h
apiname:
-	RILSENDFLASHPARAMS
product: Windows
targetos: Windows
req.typenames: RILSENDFLASHPARAMS, *LPRILSENDFLASHPARAMS
req.product: Windows 10 or later.
---

# RILSENDFLASHPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSENDFLASHPARAMS {
  DWORD       dwExecutor;
  RILADDRESS  raAddress;
} RILSENDFLASHPARAMS, RILSENDFLASHPARAMS;
````

## Members


`dwExecutor`



`raAddress`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |