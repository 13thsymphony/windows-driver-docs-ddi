---
UID: NS:rilapitypes.RILLOCATIONINFO
title: RILLOCATIONINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rillocationinfo_2.htm
old-project: netvista
ms.assetid: 057f8cb0-0473-470e-b993-457de90d98fd
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILLOCATIONINFO, RILLOCATIONINFO, RILLOCATIONINFO structure [Network Drivers Starting with Windows Vista], netvista.rillocationinfo_2, rilapitypes/RILLOCATIONINFO"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
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
````
typedef struct _RILLOCATIONINFO {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwExecutor;
  DWORD  hUiccApp;
  DWORD  dwLocationAreaCode;
  DWORD  dwTrackingAreaCode;
  DWORD  dwCellID;
} RILLOCATIONINFO, RILLOCATIONINFO;
````

## Members


`cbSize`



`dwCellID`



`dwExecutor`



`dwLocationAreaCode`



`dwParams`



`dwTrackingAreaCode`



`hUiccApp`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |