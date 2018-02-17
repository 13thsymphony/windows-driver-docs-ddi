---
UID: NS:rilapitypes.RILDMCONFIGINFOVALUE
title: RILDMCONFIGINFOVALUE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildmconfiginfovalue_2.htm
old-project: netvista
ms.assetid: 6b917b11-a2f2-4b8b-9964-2d7b4a6a1871
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rildmconfiginfovalue_2, rilapitypes/RILDMCONFIGINFOVALUE, RILDMCONFIGINFOVALUE, RILDMCONFIGINFOVALUE structure [Network Drivers Starting with Windows Vista], *LPRILDMCONFIGINFOVALUE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILDMCONFIGINFOVALUE
product: Windows
targetos: Windows
req.typenames: "*LPRILDMCONFIGINFOVALUE, RILDMCONFIGINFOVALUE"
req.product: Windows 10 or later.
---

# RILDMCONFIGINFOVALUE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILDMCONFIGINFOVALUE {
  DWORD                                cbSize;
  RILDMCONFIGINFOTYPE                  dwType;
  BOOL                                 fValue;
  DWORD                                dwValue;
  WCHAR [MAXLENGTH_DMCONFIGINFOSTRING] wszValue;
} RILDMCONFIGINFOVALUE, RILDMCONFIGINFOVALUE;
````

## Members


`cbSize`



`dwType`



`dwValue`



`fValue`



`wszValue`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |