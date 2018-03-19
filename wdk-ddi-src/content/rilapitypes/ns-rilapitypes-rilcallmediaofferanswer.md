---
UID: NS:rilapitypes.RILCALLMEDIAOFFERANSWER
title: RILCALLMEDIAOFFERANSWER
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaofferanswer.htm
old-project: netvista
ms.assetid: 6d8ad287-a4bf-4db8-9fff-a4cb1df42dda
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILCALLMEDIAOFFERANSWER, RILCALLMEDIAOFFERANSWER, RILCALLMEDIAOFFERANSWER structure [Network Drivers Starting with Windows Vista], netvista.rilcallmediaofferanswer, ntddrilapitypes/RILCALLMEDIAOFFERANSWER"
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
-	RILCALLMEDIAOFFERANSWER
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIAOFFERANSWER, *LPRILCALLMEDIAOFFERANSWER
req.product: Windows 10 or later.
---

# RILCALLMEDIAOFFERANSWER structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCALLMEDIAOFFERANSWER {
  DWORD                    cbSize;
  DWORD                    dwParams;
  RILCALLMEDIAID           stID;
  BOOL                     fChange;
  RILCALLMEDIAOFFERACTION  dwMediaAction;
  RILCALLMEDIASTATE        stOldState;
  RILCALLMEDIASTATE        stNewState;
} RILCALLMEDIAOFFERANSWER, RILCALLMEDIAOFFERANSWER;
````

## Members


`cbSize`



`dwParams`



`stID`



`fChange`



`dwMediaAction`



`stOldState`



`stNewState`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |