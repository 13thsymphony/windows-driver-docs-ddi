---
UID: NS:rilapitypes.RILNITZINFO_V1
title: RILNITZINFO_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnitzinfo_v1_2.htm
old-project: netvista
ms.assetid: ded74c48-b9a8-4ee4-8df9-3dc99892d41d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILNITZINFO_V1, RILNITZINFO_V1, RILNITZINFO_V1 structure [Network Drivers Starting with Windows Vista], netvista.rilnitzinfo_v1_2, rilapitypes/RILNITZINFO_V1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
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
-	rilapitypes.h
api_name:
-	RILNITZINFO_V1
product: Windows
targetos: Windows
req.typenames: RILNITZINFO_V1, *LPRILNITZINFO_V1
req.product: Windows 10 or later.
---

# RILNITZINFO_V1 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILNITZINFO_V1 {
  DWORD          cbSize;
  DWORD          dwParams;
  DWORD          dwExecutor;
  int            TimeZoneOffsetMinutes;
  int            DaylightSavingOffsetMinutes;
  RILSYSTEMTIME  SysTime;
} RILNITZINFO_V1, RILNITZINFO_V1;
````

## Members


`cbSize`



`DaylightSavingOffsetMinutes`



`dwExecutor`



`dwParams`



`SysTime`



`TimeZoneOffsetMinutes`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |