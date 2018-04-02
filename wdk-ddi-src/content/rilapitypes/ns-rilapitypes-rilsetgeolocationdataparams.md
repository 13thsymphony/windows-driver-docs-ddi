---
UID: NS:rilapitypes.RILSETGEOLOCATIONDATAPARAMS
title: RILSETGEOLOCATIONDATAPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetgeolocationdataparams.htm
old-project: netvista
ms.assetid: 7736c8d6-731e-4322-aade-ecd23a4fedde
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILSETGEOLOCATIONDATAPARAMS, RILSETGEOLOCATIONDATAPARAMS, RILSETGEOLOCATIONDATAPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsetgeolocationdataparams, ntddrilapitypes/RILSETGEOLOCATIONDATAPARAMS"
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
-	RILSETGEOLOCATIONDATAPARAMS
product:
- Windows
targetos: Windows
req.typenames: RILSETGEOLOCATIONDATAPARAMS, *LPRILSETGEOLOCATIONDATAPARAMS
req.product: Windows 10 or later.
---

# RILSETGEOLOCATIONDATAPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILSETGEOLOCATIONDATAPARAMS {
  DWORD                cbSize;
  DWORD                dwExecutor;
  RILOSGEOLOCATIONINFO locationInfo;
}  *LPRILSETGEOLOCATIONDATAPARAMS;
```

## Members


`cbSize`



`dwExecutor`



`locationInfo`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |