---
UID: NS:rilapitypes.RILUNSOLICITEDSSINFO_V1
title: RILUNSOLICITEDSSINFO_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilunsolicitedssinfo_v1.htm
old-project: netvista
ms.assetid: c9681207-6cdd-40b6-8878-7ea37f383e4f
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILUNSOLICITEDSSINFO_V1, RILUNSOLICITEDSSINFO_V1, RILUNSOLICITEDSSINFO_V1 structure [Network Drivers Starting with Windows Vista], netvista.rilunsolicitedssinfo_v1, ntddrilapitypes/RILUNSOLICITEDSSINFO_V1"
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
-	RILUNSOLICITEDSSINFO_V1
product: Windows
targetos: Windows
req.typenames: RILUNSOLICITEDSSINFO_V1, *LPRILUNSOLICITEDSSINFO_V1
req.product: Windows 10 or later.
---

# RILUNSOLICITEDSSINFO_V1 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILUNSOLICITEDSSINFO_V1 {
  DWORD                                cbSize;
  DWORD                                dwParams;
  DWORD                                dwExecutor;
  DWORD                                dwID;
  RILUNSOLICITEDSSINFONOTIFICATIONCODE dwNotificationCode;
  RILADDRESS                           raAddress;
  RILSUBADDRESS                        rsaSubAddress;
  DWORD                                dwCUGIndex;
}  *LPRILUNSOLICITEDSSINFO_V1;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`dwID`



`dwNotificationCode`



`raAddress`



`rsaSubAddress`



`dwCUGIndex`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |