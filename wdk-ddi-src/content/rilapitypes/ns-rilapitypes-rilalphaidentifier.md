---
UID: NS:rilapitypes.RILALPHAIDENTIFIER
title: RILALPHAIDENTIFIER
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilalphaidentifier.htm
old-project: netvista
ms.assetid: 2f7e8df5-31ae-4e1a-8dbb-89bfe8fc422d
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILALPHAIDENTIFIER, RILALPHAIDENTIFIER, RILALPHAIDENTIFIER structure [Network Drivers Starting with Windows Vista], netvista.rilalphaidentifier, ntddrilapitypes/RILALPHAIDENTIFIER"
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
-	RILALPHAIDENTIFIER
product: Windows
targetos: Windows
req.typenames: RILALPHAIDENTIFIER, *LPRILALPHAIDENTIFIER
req.product: Windows 10 or later.
---

# RILALPHAIDENTIFIER structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILALPHAIDENTIFIER {
  DWORD                   cbSize;
  DWORD                   dwParams;
  RILALPHAIDENTIFIDERTYPE dwType;
  WCHAR                   wszReason[256];
} *LPRILALPHAIDENTIFIER, RILALPHAIDENTIFIER;
```

## Members


`cbSize`



`dwParams`



`dwType`



`wszReason`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |