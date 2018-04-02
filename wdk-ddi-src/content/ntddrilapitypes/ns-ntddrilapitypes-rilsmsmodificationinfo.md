---
UID: NS:ntddrilapitypes.RILSMSMODIFICATIONINFO
title: RILSMSMODIFICATIONINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmsmodificationinfo.htm
old-project: netvista
ms.assetid: 8fed32a2-f0a7-4462-b8bb-b01c9cccf6b7
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILSMSMODIFICATIONINFO, RILSMSMODIFICATIONINFO, RILSMSMODIFICATIONINFO structure [Network Drivers Starting with Windows Vista], netvista.rilsmsmodificationinfo, ntddrilapitypes/RILSMSMODIFICATIONINFO"
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
-	RILSMSMODIFICATIONINFO
product:
- Windows
targetos: Windows
req.typenames: RILSMSMODIFICATIONINFO, *LPRILSMSMODIFICATIONINFO
---

# RILSMSMODIFICATIONINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILSMSMODIFICATIONINFO {
  DWORD              cbSize;
  DWORD              dwParams;
  DWORD              dwExecutor;
  DWORD              dwModificationType;
  RILADDRESS         raAddress;
  RILALPHAIDENTIFIER aiIdentifier;
} *LPRILSMSMODIFICATIONINFO, RILSMSMODIFICATIONINFO;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`dwModificationType`



`raAddress`



`aiIdentifier`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |