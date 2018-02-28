---
UID: NS:ntddrilapitypes.RILRFSTATE
title: RILRFSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrfstate.htm
old-project: netvista
ms.assetid: 7eb78864-d20c-4993-8b33-63096bf971fa
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILRFSTATE, RILRFSTATE, RILRFSTATE structure [Network Drivers Starting with Windows Vista], netvista.rilrfstate, ntddrilapitypes/RILRFSTATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILRFSTATE
product: Windows
targetos: Windows
req.typenames: RILRFSTATE, *LPRILRFSTATE
---

# RILRFSTATE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILRFSTATE {
  DWORD    cbSize;
  DWORD    dwParams;
  DWORD    dwRFState;
  DWORD    dwRFDataSize;
  BYTE [1] bRFData;
} RILRFSTATE, RILRFSTATE;
````

## Members


`bRFData`



`cbSize`



`dwParams`



`dwRFDataSize`



`dwRFState`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |