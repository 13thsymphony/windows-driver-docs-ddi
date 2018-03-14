---
UID: NS:rilapitypes.RILSYSTEMSELECTIONPREFS_V1
title: RILSYSTEMSELECTIONPREFS_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemselectionprefs_v1.htm
old-project: netvista
ms.assetid: a2ba47e6-9dec-46b4-ac8b-a863345f228f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILSYSTEMSELECTIONPREFS_V1, RILSYSTEMSELECTIONPREFS_V1, RILSYSTEMSELECTIONPREFS_V1 structure [Network Drivers Starting with Windows Vista], netvista.rilsystemselectionprefs_v1, ntddrilapitypes/RILSYSTEMSELECTIONPREFS_V1"
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
-	RILSYSTEMSELECTIONPREFS_V1
product: Windows
targetos: Windows
req.typenames: RILSYSTEMSELECTIONPREFS_V1, *LPRILSYSTEMSELECTIONPREFS_V1
req.product: Windows 10 or later.
---

# RILSYSTEMSELECTIONPREFS_V1 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSYSTEMSELECTIONPREFS_V1 {
  DWORD                               cbSize;
  DWORD                               dwParams;
  DWORD                               dwExecutor;
  DWORD                               dwSystemTypes;
  RILSYSTEMSELECTIONPREFSMODE         dwMode;
  RILOPERATORNAMES                    plmnInfo;
  RILSYSTEMSELECTIONPREFSROAMINGMODE  dwRoamingMode;
} RILSYSTEMSELECTIONPREFS_V1, RILSYSTEMSELECTIONPREFS_V1;
````

## Members


`cbSize`



`dwExecutor`



`dwMode`



`dwParams`



`dwRoamingMode`



`dwSystemTypes`



`plmnInfo`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |