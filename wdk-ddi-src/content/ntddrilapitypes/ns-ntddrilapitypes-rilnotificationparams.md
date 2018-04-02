---
UID: NS:ntddrilapitypes.RILNOTIFICATIONPARAMS
title: RILNOTIFICATIONPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnotificationparams.htm
old-project: netvista
ms.assetid: c89c7df3-7ccb-46db-adcc-22c49cae5108
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILNOTIFICATIONPARAMS, RILNOTIFICATIONPARAMS, RILNOTIFICATIONPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilnotificationparams, ntddrilapitypes/RILNOTIFICATIONPARAMS"
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
-	RILNOTIFICATIONPARAMS
product:
- Windows
targetos: Windows
req.typenames: RILNOTIFICATIONPARAMS, *LPRILNOTIFICATIONPARAMS
---

# RILNOTIFICATIONPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILNOTIFICATIONPARAMS {
  DWORD dwNotificationCount;
  DWORD pdwNotifications[1];
}  *LPRILNOTIFICATIONPARAMS;
```

## Members


`dwNotificationCount`



`pdwNotifications`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |