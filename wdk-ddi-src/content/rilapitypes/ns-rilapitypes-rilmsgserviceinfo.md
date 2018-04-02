---
UID: NS:rilapitypes.RILMSGSERVICEINFO
title: RILMSGSERVICEINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgserviceinfo.htm
old-project: netvista
ms.assetid: 21b1c6ef-b8f3-4230-bc3f-7ac19c6cb2d1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILMSGSERVICEINFO, RILMSGSERVICEINFO, RILMSGSERVICEINFO structure [Network Drivers Starting with Windows Vista], netvista.rilmsgserviceinfo, ntddrilapitypes/RILMSGSERVICEINFO"
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
-	RILMSGSERVICEINFO
product: Windows
targetos: Windows
req.typenames: RILMSGSERVICEINFO, *LPRILMSGSERVICEINFO
req.product: Windows 10 or later.
---

# RILMSGSERVICEINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILMSGSERVICEINFO {
  DWORD cbSize;
  DWORD dwParams;
  DWORD dwMsgSupport;
  DWORD dwStoreUsed;
  DWORD dwStoreTotal;
}  *LPRILMSGSERVICEINFO;
```

## Members


`cbSize`



`dwParams`



`dwMsgSupport`



`dwStoreUsed`



`dwStoreTotal`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |