---
UID: NS:rilapitypes.RILRANGE
title: RILRANGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrange.htm
old-project: netvista
ms.assetid: 2f704899-eb5e-4632-a76d-eb474f3273f9
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILRANGE, RILRANGE, RILRANGE structure [Network Drivers Starting with Windows Vista], netvista.rilrange, ntddrilapitypes/RILRANGE"
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
-	RILRANGE
product: Windows
targetos: Windows
req.typenames: RILRANGE, *LPRILRANGE
req.product: Windows 10 or later.
---

# RILRANGE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILRANGE {
  DWORD dwMinValue;
  DWORD dwMaxValue;
}  *LPRILRANGE;
```

## Members


`dwMinValue`



`dwMaxValue`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |