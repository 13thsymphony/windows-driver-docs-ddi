---
UID: NS:rilapitypes.RILSENDMSGPARAMS
title: RILSENDMSGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgparams.htm
old-project: netvista
ms.assetid: de1049a8-e089-4d15-baca-2c760f895894
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILSENDMSGPARAMS, RILSENDMSGPARAMS, RILSENDMSGPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsendmsgparams, ntddrilapitypes/RILSENDMSGPARAMS"
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
-	RILSENDMSGPARAMS
product: Windows
targetos: Windows
req.typenames: RILSENDMSGPARAMS, *LPRILSENDMSGPARAMS
req.product: Windows 10 or later.
---

# RILSENDMSGPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILSENDMSGPARAMS {
  DWORD      dwExecutor;
  HUICCAPP   hUiccApp;
  RILMESSAGE rmMessage;
  DWORD      dwOptions;
} *LPRILSENDMSGPARAMS, RILSENDMSGPARAMS;
```

## Members


`dwExecutor`



`hUiccApp`



`rmMessage`



`dwOptions`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |