---
UID: NS:rilapitypes.RILEXECUTORFOCUSSTATE
title: RILEXECUTORFOCUSSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexecutorfocusstate_2.htm
old-project: netvista
ms.assetid: d462092c-e40f-4685-974e-3fb31cbafa62
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILEXECUTORFOCUSSTATE, netvista.rilexecutorfocusstate_2, RILEXECUTORFOCUSSTATE, RILEXECUTORFOCUSSTATE structure [Network Drivers Starting with Windows Vista], *LPRILEXECUTORFOCUSSTATE
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
-	RILEXECUTORFOCUSSTATE
product: Windows
targetos: Windows
req.typenames: RILEXECUTORFOCUSSTATE, *LPRILEXECUTORFOCUSSTATE
req.product: Windows 10 or later.
---

# RILEXECUTORFOCUSSTATE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILEXECUTORFOCUSSTATE {
  DWORD                   cbSize;
  DWORD                   dwParams;
  DWORD                   dwNumberOfExecutors;
  BOOL [MAXNUM_EXECUTORS] fFocusStates;
} RILEXECUTORFOCUSSTATE, RILEXECUTORFOCUSSTATE;
````

## Members


`cbSize`



`dwNumberOfExecutors`



`dwParams`



`fFocusStates`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |