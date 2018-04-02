---
UID: NS:ntddrilapitypes.RILREMOTEPARTYINFO
title: RILREMOTEPARTYINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilremotepartyinfo.htm
old-project: netvista
ms.assetid: 3bcaaf63-adff-4559-9e34-eae089dff6f8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILREMOTEPARTYINFO, RILREMOTEPARTYINFO, RILREMOTEPARTYINFO structure [Network Drivers Starting with Windows Vista], netvista.rilremotepartyinfo, ntddrilapitypes/RILREMOTEPARTYINFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	RILREMOTEPARTYINFO
product: Windows
targetos: Windows
req.typenames: RILREMOTEPARTYINFO, *LPRILREMOTEPARTYINFO
---

# RILREMOTEPARTYINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILREMOTEPARTYINFO {
  DWORD                   cbSize;
  DWORD                   dwParams;
  DWORD                   dwExecutor;
  RILADDRESS              raAddress;
  RILSUBADDRESS           rsaSubAddress;
  WCHAR                   wszDescription[256];
  RILREMOTEPARTYINFOVALUE dwNumberPresentationIndicator;
  RILREMOTEPARTYINFOVALUE dwNamePresentationIndicator;
  DWORD                   dwID;
}  *LPRILREMOTEPARTYINFO;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`raAddress`



`rsaSubAddress`



`wszDescription`



`dwNumberPresentationIndicator`



`dwNamePresentationIndicator`



`dwID`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |