---
UID: NS:rilapitypes.RILEXECUTORFOCUSSTATE
title: RILEXECUTORFOCUSSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexecutorfocusstate_2.htm
old-project: netvista
ms.assetid: d462092c-e40f-4685-974e-3fb31cbafa62
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILEXECUTORFOCUSSTATE, *LPRILEXECUTORFOCUSSTATE, RILEXECUTORFOCUSSTATE
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
req.alt-api: RILEXECUTORFOCUSSTATE
req.alt-loc: rilapitypes.h
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
req.typenames: *LPRILEXECUTORFOCUSSTATE, RILEXECUTORFOCUSSTATE
req.product: Windows 10 or later.
---

# RILEXECUTORFOCUSSTATE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILEXECUTORFOCUSSTATE {
  DWORD                   cbSize;
  DWORD                   dwParams;
  DWORD                   dwNumberOfExecutors;
  BOOL [MAXNUM_EXECUTORS] fFocusStates;
} RILEXECUTORFOCUSSTATE, RILEXECUTORFOCUSSTATE;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwNumberOfExecutors


### -field fFocusStates


## -remarks
