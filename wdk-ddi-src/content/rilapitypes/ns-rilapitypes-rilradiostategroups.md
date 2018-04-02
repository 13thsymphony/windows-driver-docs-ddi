---
UID: NS:rilapitypes.RILRADIOSTATEGROUPS
title: RILRADIOSTATEGROUPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostategroups.htm
old-project: netvista
ms.assetid: 901fe9e5-4b3c-4f31-9bf0-a4a5bd66bd19
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILRADIOSTATEGROUPS, RILRADIOSTATEGROUPS, RILRADIOSTATEGROUPS structure [Network Drivers Starting with Windows Vista], netvista.rilradiostategroups, ntddrilapitypes/RILRADIOSTATEGROUPS"
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
-	RILRADIOSTATEGROUPS
product: Windows
targetos: Windows
req.typenames: RILRADIOSTATEGROUPS, *LPRILRADIOSTATEGROUPS
req.product: Windows 10 or later.
---

# RILRADIOSTATEGROUPS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILRADIOSTATEGROUPS {
  DWORD              dwCntGroups;
  RILRADIOSTATEGROUP rilGroups[1];
}  *LPRILRADIOSTATEGROUPS;
```

## Members


`dwCntGroups`



`rilGroups`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |