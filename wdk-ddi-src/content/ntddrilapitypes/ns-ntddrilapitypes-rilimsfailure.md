---
UID: NS:ntddrilapitypes.RILIMSFAILURE
title: RILIMSFAILURE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsfailure.htm
old-project: netvista
ms.assetid: 8be10470-3761-4120-8987-00d6fcc9a989
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILIMSFAILURE, RILIMSFAILURE, RILIMSFAILURE structure [Network Drivers Starting with Windows Vista], netvista.rilimsfailure, ntddrilapitypes/RILIMSFAILURE"
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
-	RILIMSFAILURE
product: Windows
targetos: Windows
req.typenames: RILIMSFAILURE, *LPRILIMSFAILURE
---

# RILIMSFAILURE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILIMSFAILURE {
  DWORD                    cbSize;
  DWORD                    dwParams;
  DWORD                    dwExecutor;
  RILIMSFAILUREMESSAGETYPE dwMessageType;
  DWORD                    dwMessageSubType;
  DWORD                    dwErrorCode;
  WCHAR                    wszErrorString[256];
} *LPRILIMSFAILURE, RILIMSFAILURE;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`dwMessageType`



`dwMessageSubType`



`dwErrorCode`



`wszErrorString`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |