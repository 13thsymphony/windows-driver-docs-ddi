---
UID: NS:ntddrilapitypes.RILLINECONTROLINFO
title: RILLINECONTROLINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rillinecontrolinfo.htm
old-project: netvista
ms.assetid: 4a3bcbda-58e8-4b40-bcc2-fe7b1e624973
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILLINECONTROLINFO, RILLINECONTROLINFO, RILLINECONTROLINFO structure [Network Drivers Starting with Windows Vista], netvista.rillinecontrolinfo, ntddrilapitypes/RILLINECONTROLINFO"
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
-	RILLINECONTROLINFO
product:
- Windows
targetos: Windows
req.typenames: RILLINECONTROLINFO, *LPRILLINECONTROLINFO
---

# RILLINECONTROLINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILLINECONTROLINFO {
  DWORD cbSize;
  DWORD dwExecutor;
  BOOL  fPolarityIncluded;
  BOOL  fToggleMode;
  BOOL  fReversePolarity;
  DWORD dwPowerDenialTime;
} *LPRILLINECONTROLINFO, RILLINECONTROLINFO;
```

## Members


`cbSize`



`dwExecutor`



`fPolarityIncluded`



`fToggleMode`



`fReversePolarity`



`dwPowerDenialTime`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |