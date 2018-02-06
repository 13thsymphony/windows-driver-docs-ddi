---
UID: NS:rilapitypes.RILCHANGEUICCLOCKPASSWORDPARAMS
title: RILCHANGEUICCLOCKPASSWORDPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilchangeuicclockpasswordparams_2.htm
old-project: netvista
ms.assetid: 24c1ae3a-31e7-4b85-8c64-f376c45cb4c4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCHANGEUICCLOCKPASSWORDPARAMS, RILCHANGEUICCLOCKPASSWORDPARAMS structure [Network Drivers Starting with Windows Vista], rilapitypes/RILCHANGEUICCLOCKPASSWORDPARAMS, *LPRILCHANGEUICCLOCKPASSWORDPARAMS, netvista.rilchangeuicclockpasswordparams_2
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
-	RILCHANGEUICCLOCKPASSWORDPARAMS
product: Windows
targetos: Windows
req.typenames: RILCHANGEUICCLOCKPASSWORDPARAMS, *LPRILCHANGEUICCLOCKPASSWORDPARAMS
req.product: Windows 10 or later.
---

# RILCHANGEUICCLOCKPASSWORDPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCHANGEUICCLOCKPASSWORDPARAMS {
  RILUICCLOCKCREDENTIAL     lockCredential;
  char [MAXLENGTH_PASSWORD] szNewPassword;
} RILCHANGEUICCLOCKPASSWORDPARAMS, RILCHANGEUICCLOCKPASSWORDPARAMS;
````

## Members


`lockCredential`



`szNewPassword`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |