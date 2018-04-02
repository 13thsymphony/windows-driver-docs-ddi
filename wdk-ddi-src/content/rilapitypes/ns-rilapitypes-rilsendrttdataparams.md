---
UID: NS:rilapitypes.RILSENDRTTDATAPARAMS
title: RILSENDRTTDATAPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendrttdataparams.htm
old-project: netvista
ms.assetid: 733b8ccc-5335-4c7e-bfc0-4618b0b3a4d8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILSENDRTTDATAPARAMS, RILSENDRTTDATAPARAMS, RILSENDRTTDATAPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsendrttdataparams, ntddrilapitypes/RILSENDRTTDATAPARAMS"
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
-	RILSENDRTTDATAPARAMS
product:
- Windows
targetos: Windows
req.typenames: RILSENDRTTDATAPARAMS, *LPRILSENDRTTDATAPARAMS
req.product: Windows 10 or later.
---

# RILSENDRTTDATAPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILSENDRTTDATAPARAMS {
  DWORD cbSize;
  DWORD dwID;
  DWORD dwExecutor;
  WCHAR wszRTTText[127];
}  *LPRILSENDRTTDATAPARAMS;
```

## Members


`cbSize`



`dwID`



`dwExecutor`



`wszRTTText`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |