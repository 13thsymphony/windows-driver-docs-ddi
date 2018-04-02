---
UID: NS:rilapitypes.RILADDCALLFORWARDINGPARAMS
title: RILADDCALLFORWARDINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladdcallforwardingparams.htm
old-project: netvista
ms.assetid: 8918552d-6a7b-414a-ab0c-a5690f109db4
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILADDCALLFORWARDINGPARAMS, RILADDCALLFORWARDINGPARAMS, RILADDCALLFORWARDINGPARAMS structure [Network Drivers Starting with Windows Vista], netvista.riladdcallforwardingparams, ntddrilapitypes/RILADDCALLFORWARDINGPARAMS"
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
-	RILADDCALLFORWARDINGPARAMS
product: Windows
targetos: Windows
req.typenames: RILADDCALLFORWARDINGPARAMS, *LPRILADDCALLFORWARDINGPARAMS
req.product: Windows 10 or later.
---

# RILADDCALLFORWARDINGPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILADDCALLFORWARDINGPARAMS {
  DWORD                           dwExecutor;
  RILCALLFORWARDINGSETTINGSREASON dwReason;
  RILCALLFORWARDINGSETTINGS       rcfsSettings;
} *LPRILADDCALLFORWARDINGPARAMS, RILADDCALLFORWARDINGPARAMS;
```

## Members


`dwExecutor`



`dwReason`



`rcfsSettings`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |