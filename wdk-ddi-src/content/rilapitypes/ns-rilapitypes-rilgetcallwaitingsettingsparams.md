---
UID: NS:rilapitypes.RILGETCALLWAITINGSETTINGSPARAMS
title: RILGETCALLWAITINGSETTINGSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetcallwaitingsettingsparams.htm
old-project: netvista
ms.assetid: b257ef88-a474-4443-8fbf-91759066a536
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILGETCALLWAITINGSETTINGSPARAMS, RILGETCALLWAITINGSETTINGSPARAMS, RILGETCALLWAITINGSETTINGSPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilgetcallwaitingsettingsparams, ntddrilapitypes/RILGETCALLWAITINGSETTINGSPARAMS"
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
-	RILGETCALLWAITINGSETTINGSPARAMS
product: Windows
targetos: Windows
req.typenames: RILGETCALLWAITINGSETTINGSPARAMS, *LPRILGETCALLWAITINGSETTINGSPARAMS
req.product: Windows 10 or later.
---

# RILGETCALLWAITINGSETTINGSPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILGETCALLWAITINGSETTINGSPARAMS {
  DWORD  dwExecutor;
  BOOL   fAllClasses;
  DWORD  dwInfoClasses;
} RILGETCALLWAITINGSETTINGSPARAMS, RILGETCALLWAITINGSETTINGSPARAMS;
````

## Members


`dwExecutor`



`fAllClasses`



`dwInfoClasses`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |