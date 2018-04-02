---
UID: NS:rilapitypes.RILSETMSGINUICCSTATUSPARAMS
title: RILSETMSGINUICCSTATUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetmsginuiccstatusparams.htm
old-project: netvista
ms.assetid: 3c35e2e0-8f8a-456f-b0ce-494a050d11dc
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILSETMSGINUICCSTATUSPARAMS, RILSETMSGINUICCSTATUSPARAMS, RILSETMSGINUICCSTATUSPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsetmsginuiccstatusparams, ntddrilapitypes/RILSETMSGINUICCSTATUSPARAMS"
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
-	RILSETMSGINUICCSTATUSPARAMS
product: Windows
targetos: Windows
req.typenames: RILSETMSGINUICCSTATUSPARAMS, *LPRILSETMSGINUICCSTATUSPARAMS
req.product: Windows 10 or later.
---

# RILSETMSGINUICCSTATUSPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILSETMSGINUICCSTATUSPARAMS {
  HUICCAPP         hUiccApp;
  DWORD            dwIndex;
  RILMESSAGESTATUS dwStatus;
}  *LPRILSETMSGINUICCSTATUSPARAMS;
```

## Members


`hUiccApp`



`dwIndex`



`dwStatus`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |