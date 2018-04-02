---
UID: NS:rilapitypes.RILADDITIONALCALLERINFO
title: RILADDITIONALCALLERINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladditionalcallerinfo.htm
old-project: netvista
ms.assetid: dd622ebc-beba-4c96-a0e8-97ad614e3937
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILADDITIONALCALLERINFO, RILADDITIONALCALLERINFO, RILADDITIONALCALLERINFO structure [Network Drivers Starting with Windows Vista], netvista.riladditionalcallerinfo, ntddrilapitypes/RILADDITIONALCALLERINFO"
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
-	RILADDITIONALCALLERINFO
product: Windows
targetos: Windows
req.typenames: RILADDITIONALCALLERINFO, *LPRILADDITIONALCALLERINFO
req.product: Windows 10 or later.
---

# RILADDITIONALCALLERINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILADDITIONALCALLERINFO {
  DWORD cbSize;
  DWORD dwParams;
  DWORD dwExecutor;
  DWORD dwCallId;
  DWORD dwCallerInfoLength;
  WCHAR wszCallerInfo[1];
} *LPRILADDITIONALCALLERINFO, RILADDITIONALCALLERINFO;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`dwCallId`



`dwCallerInfoLength`



`wszCallerInfo`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |