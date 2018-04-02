---
UID: NS:rilapitypes.RILCHANGEUICCLOCKPASSWORDPARAMS
title: RILCHANGEUICCLOCKPASSWORDPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilchangeuicclockpasswordparams.htm
old-project: netvista
ms.assetid: 00e2fe6f-fd8b-45d1-9fd2-d90c515c3571
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILCHANGEUICCLOCKPASSWORDPARAMS, RILCHANGEUICCLOCKPASSWORDPARAMS, RILCHANGEUICCLOCKPASSWORDPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilchangeuicclockpasswordparams, ntddrilapitypes/RILCHANGEUICCLOCKPASSWORDPARAMS"
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
-	RILCHANGEUICCLOCKPASSWORDPARAMS
product: Windows
targetos: Windows
req.typenames: RILCHANGEUICCLOCKPASSWORDPARAMS, *LPRILCHANGEUICCLOCKPASSWORDPARAMS
req.product: Windows 10 or later.
---

# RILCHANGEUICCLOCKPASSWORDPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILCHANGEUICCLOCKPASSWORDPARAMS {
  RILUICCLOCKCREDENTIAL lockCredential;
  char                  szNewPassword[256];
} *LPRILCHANGEUICCLOCKPASSWORDPARAMS, RILCHANGEUICCLOCKPASSWORDPARAMS;
```

## Members


`lockCredential`



`szNewPassword`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |