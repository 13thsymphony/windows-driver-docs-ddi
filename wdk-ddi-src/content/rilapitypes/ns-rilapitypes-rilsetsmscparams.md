---
UID: NS:rilapitypes.RILSETSMSCPARAMS
title: RILSETSMSCPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetsmscparams_2.htm
old-project: netvista
ms.assetid: 87c5bb45-f29d-434c-abef-acbf05c9515e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILSETSMSCPARAMS, RILSETSMSCPARAMS, RILSETSMSCPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsetsmscparams_2, rilapitypes/RILSETSMSCPARAMS"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILSETSMSCPARAMS
product: Windows
targetos: Windows
req.typenames: RILSETSMSCPARAMS, *LPRILSETSMSCPARAMS
req.product: Windows 10 or later.
---

# RILSETSMSCPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSETSMSCPARAMS {
  HUICCAPP    hUiccApp;
  RILADDRESS  raSvcCtrAddress;
} RILSETSMSCPARAMS, RILSETSMSCPARAMS;
````

## Members


`hUiccApp`



`raSvcCtrAddress`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |