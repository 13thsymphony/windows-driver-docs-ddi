---
UID: NS:rilapitypes.RILLOCATIONINFO
title: RILLOCATIONINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rillocationinfo.htm
old-project: netvista
ms.assetid: 56d35556-1e1b-422f-acbf-f52708fbf7bf
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILLOCATIONINFO, RILLOCATIONINFO, RILLOCATIONINFO structure [Network Drivers Starting with Windows Vista], netvista.rillocationinfo, ntddrilapitypes/RILLOCATIONINFO"
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
-	RILLOCATIONINFO
product: Windows
targetos: Windows
req.typenames: RILLOCATIONINFO, *LPRILLOCATIONINFO
req.product: Windows 10 or later.
---

# RILLOCATIONINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILLOCATIONINFO {
  DWORD cbSize;
  DWORD dwParams;
  DWORD dwExecutor;
  DWORD hUiccApp;
  DWORD dwLocationAreaCode;
  DWORD dwTrackingAreaCode;
  DWORD dwCellID;
} *LPRILLOCATIONINFO, RILLOCATIONINFO;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`hUiccApp`



`dwLocationAreaCode`



`dwTrackingAreaCode`



`dwCellID`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |