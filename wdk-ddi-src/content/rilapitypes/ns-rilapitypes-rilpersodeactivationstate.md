---
UID: NS:rilapitypes.RILPERSODEACTIVATIONSTATE
title: RILPERSODEACTIVATIONSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpersodeactivationstate.htm
old-project: netvista
ms.assetid: a43948e4-ab31-495a-ace2-4cb4a1119af5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILPERSODEACTIVATIONSTATE, RILPERSODEACTIVATIONSTATE, RILPERSODEACTIVATIONSTATE structure [Network Drivers Starting with Windows Vista], netvista.rilpersodeactivationstate, ntddrilapitypes/RILPERSODEACTIVATIONSTATE"
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
-	RILPERSODEACTIVATIONSTATE
product: Windows
targetos: Windows
req.typenames: RILPERSODEACTIVATIONSTATE, *LPRILPERSODEACTIVATIONSTATE
req.product: Windows 10 or later.
---

# RILPERSODEACTIVATIONSTATE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPERSODEACTIVATIONSTATE {
  DWORD                                  cbSize;
  DWORD                                  dwParams;
  RILPERSODEACTIVATIONSTATEDEPERSOSTATE  dwDePersoState;
  DWORD                                  dwNumCKAttemptsLeft;
  DWORD                                  dwNumPUKAttemptsLeft;
} RILPERSODEACTIVATIONSTATE, RILPERSODEACTIVATIONSTATE;
````

## Members


`cbSize`



`dwParams`



`dwDePersoState`



`dwNumCKAttemptsLeft`



`dwNumPUKAttemptsLeft`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |