---
UID: NS:ntddrilapitypes.RILPHONEBOOKREADYSTATE
title: RILPHONEBOOKREADYSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookreadystate.htm
old-project: netvista
ms.assetid: cd71234b-4b46-4b7b-953b-32e6f014af03
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILPHONEBOOKREADYSTATE, RILPHONEBOOKREADYSTATE, RILPHONEBOOKREADYSTATE structure [Network Drivers Starting with Windows Vista], netvista.rilphonebookreadystate, ntddrilapitypes/RILPHONEBOOKREADYSTATE"
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
-	RILPHONEBOOKREADYSTATE
product: Windows
targetos: Windows
req.typenames: RILPHONEBOOKREADYSTATE, *LPRILPHONEBOOKREADYSTATE
---

# RILPHONEBOOKREADYSTATE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILPHONEBOOKREADYSTATE {
  DWORD    cbSize;
  HUICCAPP hUiccApp;
  DWORD    dwStoreLocations;
}  *LPRILPHONEBOOKREADYSTATE;
```

## Members


`cbSize`



`hUiccApp`



`dwStoreLocations`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |