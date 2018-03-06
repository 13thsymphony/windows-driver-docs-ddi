---
UID: NS:rilapitypes.RILALPHAIDENTIFIER
title: RILALPHAIDENTIFIER
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilalphaidentifier_2.htm
old-project: netvista
ms.assetid: 40656b8d-3921-420e-9577-12ba272aa72c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILALPHAIDENTIFIER, RILALPHAIDENTIFIER, RILALPHAIDENTIFIER structure [Network Drivers Starting with Windows Vista], netvista.rilalphaidentifier_2, rilapitypes/RILALPHAIDENTIFIER"
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
-	RILALPHAIDENTIFIER
product: Windows
targetos: Windows
req.typenames: RILALPHAIDENTIFIER, *LPRILALPHAIDENTIFIER
req.product: Windows 10 or later.
---

# RILALPHAIDENTIFIER structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILALPHAIDENTIFIER {
  DWORD                     cbSize;
  DWORD                     dwParams;
  RILALPHAIDENTIFIDERTYPE   dwType;
  WCHAR [MAXLENGTH_ERRLONG] wszReason;
} RILALPHAIDENTIFIER, RILALPHAIDENTIFIER;
````

## Members


`cbSize`



`dwParams`



`dwType`



`wszReason`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |