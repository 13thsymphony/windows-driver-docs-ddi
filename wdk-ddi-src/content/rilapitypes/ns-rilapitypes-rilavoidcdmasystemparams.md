---
UID: NS:rilapitypes.RILAVOIDCDMASYSTEMPARAMS
title: RILAVOIDCDMASYSTEMPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilavoidcdmasystemparams_2.htm
old-project: netvista
ms.assetid: bd938bd9-479a-434c-91d6-93ec76ebe5d6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILAVOIDCDMASYSTEMPARAMS, netvista.rilavoidcdmasystemparams_2, RILAVOIDCDMASYSTEMPARAMS, rilapitypes/RILAVOIDCDMASYSTEMPARAMS, RILAVOIDCDMASYSTEMPARAMS structure [Network Drivers Starting with Windows Vista]"
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
-	RILAVOIDCDMASYSTEMPARAMS
product: Windows
targetos: Windows
req.typenames: RILAVOIDCDMASYSTEMPARAMS, *LPRILAVOIDCDMASYSTEMPARAMS
req.product: Windows 10 or later.
---

# RILAVOIDCDMASYSTEMPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILAVOIDCDMASYSTEMPARAMS {
  DWORD                       dwExecutor;
  RILCDMAAVOIDANCEREQUESTYPE  dwAvoidanceReqType;
} RILAVOIDCDMASYSTEMPARAMS, RILAVOIDCDMASYSTEMPARAMS;
````

## Members


`dwAvoidanceReqType`



`dwExecutor`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |