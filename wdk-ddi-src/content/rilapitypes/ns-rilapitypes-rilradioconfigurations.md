---
UID: NS:rilapitypes.RILRADIOCONFIGURATIONS
title: RILRADIOCONFIGURATIONS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradioconfigurations.htm
old-project: netvista
ms.assetid: 28908305-69aa-4bf0-98a1-6cee4aa1c349
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILRADIOCONFIGURATIONS, RILRADIOCONFIGURATIONS, RILRADIOCONFIGURATIONS structure [Network Drivers Starting with Windows Vista], netvista.rilradioconfigurations, ntddrilapitypes/RILRADIOCONFIGURATIONS"
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
-	RILRADIOCONFIGURATIONS
product: Windows
targetos: Windows
req.typenames: RILRADIOCONFIGURATIONS, *LPRILRADIOCONFIGURATIONS
req.product: Windows 10 or later.
---

# RILRADIOCONFIGURATIONS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILRADIOCONFIGURATIONS {
  DWORD                 dwNumberOfConfigurations;
  RILRADIOCONFIGURATION stConfigurations[1];
} *LPRILRADIOCONFIGURATIONS, RILRADIOCONFIGURATIONS;
```

## Members


`dwNumberOfConfigurations`



`stConfigurations`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |