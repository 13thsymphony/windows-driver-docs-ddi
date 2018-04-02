---
UID: NS:ntddrilapitypes.RILCALLMODIFICATIONINFO
title: RILCALLMODIFICATIONINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationinfo.htm
old-project: netvista
ms.assetid: 568603d9-0f96-49f7-a6f8-3c69d889cea7
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILCALLMODIFICATIONINFO, RILCALLMODIFICATIONINFO, RILCALLMODIFICATIONINFO structure [Network Drivers Starting with Windows Vista], netvista.rilcallmodificationinfo, ntddrilapitypes/RILCALLMODIFICATIONINFO"
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
-	RILCALLMODIFICATIONINFO
product:
- Windows
targetos: Windows
req.typenames: RILCALLMODIFICATIONINFO, *LPRILCALLMODIFICATIONINFO
---

# RILCALLMODIFICATIONINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILCALLMODIFICATIONINFO {
  DWORD                                   cbSize;
  DWORD                                   dwParams;
  DWORD                                   dwExecutor;
  DWORD                                   dwID;
  RILCALLMODIFICATIONINFOMODIFICATIONTYPE dwModificationType;
  RILCALLTYPE                             dwOldCallType;
  RILCALLTYPE                             dwNewCallType;
  RILADDRESS                              raAddress;
  RILALPHAIDENTIFIER                      aiIdentifier;
}  *LPRILCALLMODIFICATIONINFO;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`dwID`



`dwModificationType`



`dwOldCallType`



`dwNewCallType`



`raAddress`



`aiIdentifier`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |