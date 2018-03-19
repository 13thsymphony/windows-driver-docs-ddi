---
UID: NS:rilapitypes.RILEXECUTORFOCUSSTATE
title: RILEXECUTORFOCUSSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexecutorfocusstate.htm
old-project: netvista
ms.assetid: 74fc88c0-3edf-4831-a03b-4ace6ca2ec04
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILEXECUTORFOCUSSTATE, RILEXECUTORFOCUSSTATE, RILEXECUTORFOCUSSTATE structure [Network Drivers Starting with Windows Vista], netvista.rilexecutorfocusstate, ntddrilapitypes/RILEXECUTORFOCUSSTATE"
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
  DWORD    cbSize;
  DWORD    dwParams;
  DWORD    dwNumberOfExecutors;
  BOOL [2] fFocusStates;
} RILEXECUTORFOCUSSTATE, RILEXECUTORFOCUSSTATE;
````

## Members


`cbSize`



`dwParams`



`dwNumberOfExecutors`



`fFocusStates`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |