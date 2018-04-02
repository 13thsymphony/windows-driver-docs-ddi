---
UID: NS:rilapitypes.RILSETNOTIFICATIONFILTERSTATEPARAMS
title: RILSETNOTIFICATIONFILTERSTATEPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetnotificationfilterstateparams.htm
old-project: netvista
ms.assetid: bd30a156-0414-486c-92c4-21c33d32f9b8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILSETNOTIFICATIONFILTERSTATEPARAMS, RILSETNOTIFICATIONFILTERSTATEPARAMS, RILSETNOTIFICATIONFILTERSTATEPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsetnotificationfilterstateparams, ntddrilapitypes/RILSETNOTIFICATIONFILTERSTATEPARAMS"
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
-	RILSETNOTIFICATIONFILTERSTATEPARAMS
product: Windows
targetos: Windows
req.typenames: RILSETNOTIFICATIONFILTERSTATEPARAMS, *LPRILSETNOTIFICATIONFILTERSTATEPARAMS
req.product: Windows 10 or later.
---

# RILSETNOTIFICATIONFILTERSTATEPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILSETNOTIFICATIONFILTERSTATEPARAMS {
  DWORD dwFilterMask;
  DWORD dwFilterState;
}  *LPRILSETNOTIFICATIONFILTERSTATEPARAMS;
```

## Members


`dwFilterMask`



`dwFilterState`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |