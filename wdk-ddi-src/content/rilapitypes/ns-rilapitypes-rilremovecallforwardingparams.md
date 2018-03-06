---
UID: NS:rilapitypes.RILREMOVECALLFORWARDINGPARAMS
title: RILREMOVECALLFORWARDINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilremovecallforwardingparams_2.htm
old-project: netvista
ms.assetid: 5bdd8542-e1ef-42ac-99d7-c004039d2f33
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILREMOVECALLFORWARDINGPARAMS, RILREMOVECALLFORWARDINGPARAMS, RILREMOVECALLFORWARDINGPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilremovecallforwardingparams_2, rilapitypes/RILREMOVECALLFORWARDINGPARAMS"
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
-	RILREMOVECALLFORWARDINGPARAMS
product: Windows
targetos: Windows
req.typenames: RILREMOVECALLFORWARDINGPARAMS, *LPRILREMOVECALLFORWARDINGPARAMS
req.product: Windows 10 or later.
---

# RILREMOVECALLFORWARDINGPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILREMOVECALLFORWARDINGPARAMS {
  DWORD                            dwExecutor;
  RILCALLFORWARDINGSETTINGSREASON  dwReason;
  DWORD                            dwInfoClasses;
} RILREMOVECALLFORWARDINGPARAMS, RILREMOVECALLFORWARDINGPARAMS;
````

## Members


`dwExecutor`



`dwInfoClasses`



`dwReason`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |