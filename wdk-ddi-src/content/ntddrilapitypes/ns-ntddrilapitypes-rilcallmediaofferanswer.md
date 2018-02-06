---
UID: NS:ntddrilapitypes.RILCALLMEDIAOFFERANSWER
title: RILCALLMEDIAOFFERANSWER
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaofferanswer.htm
old-project: netvista
ms.assetid: 6d8ad287-a4bf-4db8-9fff-a4cb1df42dda
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCALLMEDIAOFFERANSWER structure [Network Drivers Starting with Windows Vista], RILCALLMEDIAOFFERANSWER, ntddrilapitypes/RILCALLMEDIAOFFERANSWER, netvista.rilcallmediaofferanswer, *LPRILCALLMEDIAOFFERANSWER
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILCALLMEDIAOFFERANSWER
product: Windows
targetos: Windows
req.typenames: "*LPRILCALLMEDIAOFFERANSWER, RILCALLMEDIAOFFERANSWER"
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



`dwMediaAction`



`dwParams`



`fChange`



`stID`



`stNewState`



`stOldState`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |