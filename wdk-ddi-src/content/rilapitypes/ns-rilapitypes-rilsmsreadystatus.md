---
UID: NS:rilapitypes.RILSMSREADYSTATUS
title: RILSMSREADYSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmsreadystatus.htm
old-project: netvista
ms.assetid: 0f2d6a06-18af-4e7a-9f88-c81d98575f56
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILSMSREADYSTATUS, RILSMSREADYSTATUS, RILSMSREADYSTATUS structure [Network Drivers Starting with Windows Vista], netvista.rilsmsreadystatus, ntddrilapitypes/RILSMSREADYSTATUS"
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
-	RILSMSREADYSTATUS
product: Windows
targetos: Windows
req.typenames: RILSMSREADYSTATUS, *LPRILSMSREADYSTATUS
req.product: Windows 10 or later.
---

# RILSMSREADYSTATUS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILSMSREADYSTATUS {
  DWORD            cbSize;
  DWORD            dwParams;
  DWORD            dwExecutor;
  RILSMSREADYSTATE dwReadyState;
} *LPRILSMSREADYSTATUS, RILSMSREADYSTATUS;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`dwReadyState`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |