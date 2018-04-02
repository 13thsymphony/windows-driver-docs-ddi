---
UID: NS:rilapitypes.RILSETEXECUTORFOCUSPARAMS
title: RILSETEXECUTORFOCUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetexecutorfocusparams.htm
old-project: netvista
ms.assetid: 5e9f9ef1-e86e-49a7-be76-a31595da28e6
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILSETEXECUTORFOCUSPARAMS, RILSETEXECUTORFOCUSPARAMS, RILSETEXECUTORFOCUSPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsetexecutorfocusparams, ntddrilapitypes/RILSETEXECUTORFOCUSPARAMS"
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
-	RILSETEXECUTORFOCUSPARAMS
product:
- Windows
targetos: Windows
req.typenames: RILSETEXECUTORFOCUSPARAMS, *LPRILSETEXECUTORFOCUSPARAMS
req.product: Windows 10 or later.
---

# RILSETEXECUTORFOCUSPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILSETEXECUTORFOCUSPARAMS {
  DWORD dwNumberOfExecutors;
  BOOL  fFocusStates[2];
}  *LPRILSETEXECUTORFOCUSPARAMS;
```

## Members


`dwNumberOfExecutors`



`fFocusStates`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |