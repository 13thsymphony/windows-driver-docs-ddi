---
UID: NS:rilapitypes.RILGETCALLFORWARDINGPARAMS
title: RILGETCALLFORWARDINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetcallforwardingparams.htm
old-project: netvista
ms.assetid: 94e24172-a149-4e74-9600-2fcb7396ef34
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILGETCALLFORWARDINGPARAMS, RILGETCALLFORWARDINGPARAMS, RILGETCALLFORWARDINGPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilgetcallforwardingparams, ntddrilapitypes/RILGETCALLFORWARDINGPARAMS"
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
-	RILGETCALLFORWARDINGPARAMS
product: Windows
targetos: Windows
req.typenames: RILGETCALLFORWARDINGPARAMS, *LPRILGETCALLFORWARDINGPARAMS
req.product: Windows 10 or later.
---

# RILGETCALLFORWARDINGPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILGETCALLFORWARDINGPARAMS {
  DWORD                           dwExecutor;
  RILCALLFORWARDINGSETTINGSREASON dwReason;
  BOOL                            fAllClasses;
  DWORD                           dwInfoClasses;
}  *LPRILGETCALLFORWARDINGPARAMS;
```

## Members


`dwExecutor`



`dwReason`



`fAllClasses`



`dwInfoClasses`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |