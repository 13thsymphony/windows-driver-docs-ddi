---
UID: NS:ntddrilapitypes.RILMANAGECALLSPARAMS_V2
title: RILMANAGECALLSPARAMS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmanagecallsparams_v2.htm
old-project: netvista
ms.assetid: 7a4e0930-b499-4abd-bbf6-326ae928b5c5
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILMANAGECALLSPARAMS_V2, RILMANAGECALLSPARAMS_V2, RILMANAGECALLSPARAMS_V2 structure [Network Drivers Starting with Windows Vista], netvista.rilmanagecallsparams_v2, ntddrilapitypes/RILMANAGECALLSPARAMS_V2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	RILMANAGECALLSPARAMS_V2
product: Windows
targetos: Windows
req.typenames: RILMANAGECALLSPARAMS_V2, *LPRILMANAGECALLSPARAMS_V2
---

# RILMANAGECALLSPARAMS_V2 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILMANAGECALLSPARAMS_V2 {
  DWORD                      dwExecutor;
  RILMANAGECALLPARAMSCOMMAND dwCommand;
  DWORD                      dwID;
  BOOL                       fHasOfferAnswer;
  RILCALLMEDIAOFFERANSWERSET rcmOfferAnswer;
} *LPRILMANAGECALLSPARAMS_V2, RILMANAGECALLSPARAMS_V2;
```

## Members


`dwExecutor`



`dwCommand`



`dwID`



`fHasOfferAnswer`



`rcmOfferAnswer`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |