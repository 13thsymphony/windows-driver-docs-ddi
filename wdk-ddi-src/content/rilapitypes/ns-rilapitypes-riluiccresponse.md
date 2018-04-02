---
UID: NS:rilapitypes.RILUICCRESPONSE
title: RILUICCRESPONSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccresponse.htm
old-project: netvista
ms.assetid: c584e508-b0f1-4809-808e-089e9a7fbcf9
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILUICCRESPONSE, RILUICCRESPONSE, RILUICCRESPONSE structure [Network Drivers Starting with Windows Vista], netvista.riluiccresponse, ntddrilapitypes/RILUICCRESPONSE"
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
-	RILUICCRESPONSE
product:
- Windows
targetos: Windows
req.typenames: RILUICCRESPONSE, *LPRILUICCRESPONSE
req.product: Windows 10 or later.
---

# RILUICCRESPONSE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILUICCRESPONSE {
  DWORD cbSize;
  DWORD dwParams;
  DWORD dwStatusWord1;
  DWORD dwStatusWord2;
  DWORD dwResponseSize;
  BYTE  pbResponse[1];
}  *LPRILUICCRESPONSE;
```

## Members


`cbSize`



`dwParams`



`dwStatusWord1`



`dwStatusWord2`



`dwResponseSize`



`pbResponse`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |