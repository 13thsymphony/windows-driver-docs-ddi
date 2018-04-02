---
UID: NS:rilapitypes.RILCALLMEDIAOFFERANSWERSET
title: RILCALLMEDIAOFFERANSWERSET
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaofferanswerset.htm
old-project: netvista
ms.assetid: 5d2f913e-10a3-4e96-a12f-5c4ea1dc061f
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILCALLMEDIAOFFERANSWERSET, RILCALLMEDIAOFFERANSWERSET, RILCALLMEDIAOFFERANSWERSET structure [Network Drivers Starting with Windows Vista], netvista.rilcallmediaofferanswerset, ntddrilapitypes/RILCALLMEDIAOFFERANSWERSET"
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
-	RILCALLMEDIAOFFERANSWERSET
product:
- Windows
targetos: Windows
req.typenames: RILCALLMEDIAOFFERANSWERSET, *LPRILCALLMEDIAOFFERANSWERSET
req.product: Windows 10 or later.
---

# RILCALLMEDIAOFFERANSWERSET structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILCALLMEDIAOFFERANSWERSET {
  DWORD                       cbSize;
  RILCALLMEDIAOFFERANSWERTYPE dwType;
  DWORD                       dwNumberOfItems;
  RILCALLMEDIAOFFERANSWER     stOfferAnswer[4];
}  *LPRILCALLMEDIAOFFERANSWERSET;
```

## Members


`cbSize`



`dwType`



`dwNumberOfItems`



`stOfferAnswer`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |