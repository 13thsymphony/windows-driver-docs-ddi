---
UID: NS:rilapitypes.RILSYSTEMSELECTIONPREFS_V2
title: RILSYSTEMSELECTIONPREFS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemselectionprefs_v2.htm
old-project: netvista
ms.assetid: 0734fac3-9327-4765-a50b-57be45ce2817
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILSYSTEMSELECTIONPREFS, *LPRILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS, RILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS_V2 structure [Network Drivers Starting with Windows Vista], netvista.rilsystemselectionprefs_v2, ntddrilapitypes/RILSYSTEMSELECTIONPREFS_V2"
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
-	RILSYSTEMSELECTIONPREFS_V2
product:
- Windows
targetos: Windows
req.typenames: RILSYSTEMSELECTIONPREFS_V2, *LPRILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS, *LPRILSYSTEMSELECTIONPREFS
req.product: Windows 10 or later.
---

# RILSYSTEMSELECTIONPREFS_V2 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILSYSTEMSELECTIONPREFS_V2 {
  DWORD                              cbSize;
  DWORD                              dwParams;
  DWORD                              dwExecutor;
  DWORD                              dwSystemTypes;
  RILSYSTEMSELECTIONPREFSMODE        dwMode;
  RILOPERATORNAMES                   plmnInfo;
  RILSYSTEMSELECTIONPREFSROAMINGMODE dwRoamingMode;
  DWORD                              dwAcquisitionOrderSize;
  DWORD                              AcquisitionOrder[16];
} RILSYSTEMSELECTIONPREFS, RILSYSTEMSELECTIONPREFS_V2, *LPRILSYSTEMSELECTIONPREFS_V2, *LPRILSYSTEMSELECTIONPREFS;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`dwSystemTypes`



`dwMode`



`plmnInfo`



`dwRoamingMode`



`dwAcquisitionOrderSize`



`AcquisitionOrder`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |