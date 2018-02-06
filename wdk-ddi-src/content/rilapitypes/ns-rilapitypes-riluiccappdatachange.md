---
UID: NS:rilapitypes.RILUICCAPPDATACHANGE
title: RILUICCAPPDATACHANGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappdatachange_2.htm
old-project: netvista
ms.assetid: b812cd5d-73a1-42bc-a1ae-1c1494369288
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILUICCAPPDATACHANGE structure [Network Drivers Starting with Windows Vista], *LPRILUICCAPPDATACHANGE, RILUICCAPPDATACHANGE, netvista.riluiccappdatachange_2, rilapitypes/RILUICCAPPDATACHANGE
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
-	RILUICCAPPDATACHANGE
product: Windows
targetos: Windows
req.typenames: "*LPRILUICCAPPDATACHANGE, RILUICCAPPDATACHANGE"
req.product: Windows 10 or later.
---

# RILUICCAPPDATACHANGE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCAPPDATACHANGE {
  DWORD                     cbSize;
  HUICCAPP                  hUiccApp;
  RILUICCAPPDATACHANGEENUM  dwDataChange;
} RILUICCAPPDATACHANGE, RILUICCAPPDATACHANGE;
````

## Members


`cbSize`



`dwDataChange`



`hUiccApp`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |