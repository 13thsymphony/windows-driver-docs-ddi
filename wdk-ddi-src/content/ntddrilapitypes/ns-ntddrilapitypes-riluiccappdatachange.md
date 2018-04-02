---
UID: NS:ntddrilapitypes.RILUICCAPPDATACHANGE
title: RILUICCAPPDATACHANGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappdatachange.htm
old-project: netvista
ms.assetid: a551f469-96f4-42cf-826d-3557cc13ce29
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILUICCAPPDATACHANGE, RILUICCAPPDATACHANGE, RILUICCAPPDATACHANGE structure [Network Drivers Starting with Windows Vista], netvista.riluiccappdatachange, ntddrilapitypes/RILUICCAPPDATACHANGE"
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
-	RILUICCAPPDATACHANGE
product: Windows
targetos: Windows
req.typenames: RILUICCAPPDATACHANGE, *LPRILUICCAPPDATACHANGE
---

# RILUICCAPPDATACHANGE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILUICCAPPDATACHANGE {
  DWORD                    cbSize;
  HUICCAPP                 hUiccApp;
  RILUICCAPPDATACHANGEENUM dwDataChange;
} *LPRILUICCAPPDATACHANGE, RILUICCAPPDATACHANGE;
```

## Members


`cbSize`



`hUiccApp`



`dwDataChange`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |