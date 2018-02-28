---
UID: NS:rilapitypes.RILGETCALLFORWARDINGPARAMS
title: RILGETCALLFORWARDINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetcallforwardingparams_2.htm
old-project: netvista
ms.assetid: f7ebe2a7-b29e-411e-bdfa-744c95645095
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILGETCALLFORWARDINGPARAMS, RILGETCALLFORWARDINGPARAMS, RILGETCALLFORWARDINGPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilgetcallforwardingparams_2, rilapitypes/RILGETCALLFORWARDINGPARAMS"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
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
````
typedef struct _RILGETCALLFORWARDINGPARAMS {
  DWORD                            dwExecutor;
  RILCALLFORWARDINGSETTINGSREASON  dwReason;
  BOOL                             fAllClasses;
  DWORD                            dwInfoClasses;
} RILGETCALLFORWARDINGPARAMS, RILGETCALLFORWARDINGPARAMS;
````

## Members


`dwExecutor`



`dwInfoClasses`



`dwReason`



`fAllClasses`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |