---
UID: NS:rilapitypes.RILOPERATORINFO
title: RILOPERATORINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riloperatorinfo.htm
old-project: netvista
ms.assetid: 213a4d4e-d19a-40c4-9bc4-8cf6f8aa2d07
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILOPERATORINFO, RILOPERATORINFO, RILOPERATORINFO structure [Network Drivers Starting with Windows Vista], netvista.riloperatorinfo, ntddrilapitypes/RILOPERATORINFO"
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
-	RILOPERATORINFO
product: Windows
targetos: Windows
req.typenames: RILOPERATORINFO, *LPRILOPERATORINFO
req.product: Windows 10 or later.
---

# RILOPERATORINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILOPERATORINFO {
  DWORD                  cbSize;
  DWORD                  dwParams;
  DWORD                  dwIndex;
  RILOPERATORINFOSTATUS  dwStatus;
  RILOPERATORNAMES       ronNames;
} RILOPERATORINFO, RILOPERATORINFO;
````

## Members


`cbSize`



`dwIndex`



`dwParams`



`dwStatus`



`ronNames`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |