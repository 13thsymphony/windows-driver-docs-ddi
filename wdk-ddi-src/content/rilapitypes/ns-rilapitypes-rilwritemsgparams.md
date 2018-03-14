---
UID: NS:rilapitypes.RILWRITEMSGPARAMS
title: RILWRITEMSGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilwritemsgparams.htm
old-project: netvista
ms.assetid: d66d63cd-ec34-4749-9ed9-38ee6d962ea5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILWRITEMSGPARAMS, RILWRITEMSGPARAMS, RILWRITEMSGPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilwritemsgparams, ntddrilapitypes/RILWRITEMSGPARAMS"
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
-	RILWRITEMSGPARAMS
product: Windows
targetos: Windows
req.typenames: RILWRITEMSGPARAMS, *LPRILWRITEMSGPARAMS
req.product: Windows 10 or later.
---

# RILWRITEMSGPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILWRITEMSGPARAMS {
  HUICCAPP          hUiccApp;
  RILMESSAGE        rmMessage;
  RILMESSAGESTATUS  dwStatus;
} RILWRITEMSGPARAMS, RILWRITEMSGPARAMS;
````

## Members


`dwStatus`



`hUiccApp`



`rmMessage`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |