---
UID: NS:rilapitypes.RILRTTDATA
title: RILRTTDATA
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrttdata.htm
old-project: netvista
ms.assetid: 037831c7-d0ef-4cbc-a414-a77010e228a5
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILRTTDATA, RILRTTDATA, RILRTTDATA structure [Network Drivers Starting with Windows Vista], netvista.rilrttdata, ntddrilapitypes/RILRTTDATA"
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
-	RILRTTDATA
product:
- Windows
targetos: Windows
req.typenames: RILRTTDATA, *LPRILRTTDATA
req.product: Windows 10 or later.
---

# RILRTTDATA structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILRTTDATA {
  DWORD cbSize;
  DWORD dwID;
  DWORD dwExecutor;
  WCHAR wszRTTData[127];
}  *LPRILRTTDATA;
```

## Members


`cbSize`



`dwID`



`dwExecutor`



`wszRTTData`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |