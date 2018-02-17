---
UID: NS:rilapitypes.RILSETCALLBARRINGSTATUSPARAMS
title: RILSETCALLBARRINGSTATUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetcallbarringstatusparams_2.htm
old-project: netvista
ms.assetid: 6116e564-93e6-45ba-8759-aab7d82783b2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSETCALLBARRINGSTATUSPARAMS, RILSETCALLBARRINGSTATUSPARAMS structure [Network Drivers Starting with Windows Vista], rilapitypes/RILSETCALLBARRINGSTATUSPARAMS, netvista.rilsetcallbarringstatusparams_2, *LPRILSETCALLBARRINGSTATUSPARAMS
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
-	RILSETCALLBARRINGSTATUSPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILSETCALLBARRINGSTATUSPARAMS, RILSETCALLBARRINGSTATUSPARAMS"
req.product: Windows 10 or later.
---

# RILSETCALLBARRINGSTATUSPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSETCALLBARRINGSTATUSPARAMS {
  DWORD                             dwExecutor;
  RILCALLBARRINGSTATUSPARAMSTYPE    dwType;
  BOOL                              fAllClasses;
  DWORD                             dwInfoClasses;
  BOOL                              fPassword;
  char [MAXLENGTH_PASSWORD]         szPassword;
  RILCALLBARRINGSTATUSPARAMSSTATUS  dwStatus;
} RILSETCALLBARRINGSTATUSPARAMS, RILSETCALLBARRINGSTATUSPARAMS;
````

## Members


`dwExecutor`



`dwInfoClasses`



`dwStatus`



`dwType`



`fAllClasses`



`fPassword`



`szPassword`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |