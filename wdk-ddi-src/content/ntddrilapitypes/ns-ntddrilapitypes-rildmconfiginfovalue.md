---
UID: NS:ntddrilapitypes.RILDMCONFIGINFOVALUE
title: RILDMCONFIGINFOVALUE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildmconfiginfovalue.htm
old-project: netvista
ms.assetid: dda43544-4609-4674-9616-8e09939f0c39
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILDMCONFIGINFOVALUE, RILDMCONFIGINFOVALUE, RILDMCONFIGINFOVALUE structure [Network Drivers Starting with Windows Vista], netvista.rildmconfiginfovalue, ntddrilapitypes/RILDMCONFIGINFOVALUE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILDMCONFIGINFOVALUE
product: Windows
targetos: Windows
req.typenames: RILDMCONFIGINFOVALUE, *LPRILDMCONFIGINFOVALUE
---

# RILDMCONFIGINFOVALUE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILDMCONFIGINFOVALUE {
  DWORD                cbSize;
  RILDMCONFIGINFOTYPE  dwType;
  BOOL                 fValue;
  DWORD                dwValue;
  WCHAR [256]          wszValue;
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
| **Header** | ntddrilapitypes.h |