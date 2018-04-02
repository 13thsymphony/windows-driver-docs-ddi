---
UID: NS:ntddrilapitypes.RILGETPHONEBOOKOPTIONSPARAMS
title: RILGETPHONEBOOKOPTIONSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetphonebookoptionsparams.htm
old-project: netvista
ms.assetid: a6c71f2d-baf7-4293-ae13-38625be3ab3f
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILGETPHONEBOOKOPTIONSPARAMS, RILGETPHONEBOOKOPTIONSPARAMS, RILGETPHONEBOOKOPTIONSPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilgetphonebookoptionsparams, ntddrilapitypes/RILGETPHONEBOOKOPTIONSPARAMS"
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
-	RILGETPHONEBOOKOPTIONSPARAMS
product:
- Windows
targetos: Windows
req.typenames: RILGETPHONEBOOKOPTIONSPARAMS, *LPRILGETPHONEBOOKOPTIONSPARAMS
---

# RILGETPHONEBOOKOPTIONSPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILGETPHONEBOOKOPTIONSPARAMS {
  HUICCAPP                   hUiccApp;
  RILPHONEENTRYSTORELOCATION dwStoreLocation;
}  *LPRILGETPHONEBOOKOPTIONSPARAMS;
```

## Members


`hUiccApp`



`dwStoreLocation`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |