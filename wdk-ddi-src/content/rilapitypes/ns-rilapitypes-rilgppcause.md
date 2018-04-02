---
UID: NS:rilapitypes.RILGPPCAUSE
title: RILGPPCAUSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgppcause.htm
old-project: netvista
ms.assetid: 4072183a-36b5-4a77-a1a5-95b97950b01a
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILGPPCAUSE, RILGPPCAUSE, RILGPPCAUSE structure [Network Drivers Starting with Windows Vista], netvista.rilgppcause, ntddrilapitypes/RILGPPCAUSE"
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
-	RILGPPCAUSE
product: Windows
targetos: Windows
req.typenames: RILGPPCAUSE, *LPRILGPPCAUSE
req.product: Windows 10 or later.
---

# RILGPPCAUSE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILGPPCAUSE {
  DWORD dwLocation;
  DWORD dwCauseValue;
} *LPRILGPPCAUSE, RILGPPCAUSE;
```

## Members


`dwLocation`



`dwCauseValue`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |