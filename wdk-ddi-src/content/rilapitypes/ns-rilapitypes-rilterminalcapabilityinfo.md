---
UID: NS:rilapitypes.RILTERMINALCAPABILITYINFO
title: RILTERMINALCAPABILITYINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilterminalcapabilityinfo.htm
old-project: netvista
ms.assetid: e6ad67bf-cd16-469e-af49-6a640a4319c0
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILTERMINALCAPABILITYINFO, RILTERMINALCAPABILITYINFO, RILTERMINALCAPABILITYINFO structure [Network Drivers Starting with Windows Vista], netvista.rilterminalcapabilityinfo, ntddrilapitypes/RILTERMINALCAPABILITYINFO"
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
-	RILTERMINALCAPABILITYINFO
product: Windows
targetos: Windows
req.typenames: RILTERMINALCAPABILITYINFO, *LPRILTERMINALCAPABILITYINFO
req.product: Windows 10 or later.
---

# RILTERMINALCAPABILITYINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILTERMINALCAPABILITYINFO {
  DWORD dwSize;
  BYTE  bData[256];
} *LPRILTERMINALCAPABILITYINFO, RILTERMINALCAPABILITYINFO;
```

## Members


`dwSize`



`bData`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |