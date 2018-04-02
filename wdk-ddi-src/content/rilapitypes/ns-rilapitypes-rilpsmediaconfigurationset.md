---
UID: NS:rilapitypes.RILPSMEDIACONFIGURATIONSET
title: RILPSMEDIACONFIGURATIONSET
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpsmediaconfigurationset.htm
old-project: netvista
ms.assetid: b41f6539-293f-47ed-b720-5053574a1841
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILPSMEDIACONFIGURATIONSET, RILPSMEDIACONFIGURATIONSET, RILPSMEDIACONFIGURATIONSET structure [Network Drivers Starting with Windows Vista], netvista.rilpsmediaconfigurationset, ntddrilapitypes/RILPSMEDIACONFIGURATIONSET"
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
-	RILPSMEDIACONFIGURATIONSET
product:
- Windows
targetos: Windows
req.typenames: RILPSMEDIACONFIGURATIONSET, *LPRILPSMEDIACONFIGURATIONSET
req.product: Windows 10 or later.
---

# RILPSMEDIACONFIGURATIONSET structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILPSMEDIACONFIGURATIONSET {
  DWORD                   cbSize;
  DWORD                   dwExecutor;
  DWORD                   dwNumMediaConfiguration;
  RILPSMEDIACONFIGURATION stMediaConfiguration[1];
} *LPRILPSMEDIACONFIGURATIONSET, RILPSMEDIACONFIGURATIONSET;
```

## Members


`cbSize`



`dwExecutor`



`dwNumMediaConfiguration`



`stMediaConfiguration`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |