---
UID: NS:rilapitypes.RILWRITEADDITIONALNUMBERSTRINGPARAMS
title: RILWRITEADDITIONALNUMBERSTRINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilwriteadditionalnumberstringparams.htm
old-project: netvista
ms.assetid: 2adcf421-c651-46a5-b82a-db62591e69f0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILWRITEADDITIONALNUMBERSTRINGPARAMS, RILWRITEADDITIONALNUMBERSTRINGPARAMS, RILWRITEADDITIONALNUMBERSTRINGPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilwriteadditionalnumberstringparams, ntddrilapitypes/RILWRITEADDITIONALNUMBERSTRINGPARAMS"
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
-	RILWRITEADDITIONALNUMBERSTRINGPARAMS
product: Windows
targetos: Windows
req.typenames: RILWRITEADDITIONALNUMBERSTRINGPARAMS, *LPRILWRITEADDITIONALNUMBERSTRINGPARAMS
req.product: Windows 10 or later.
---

# RILWRITEADDITIONALNUMBERSTRINGPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILWRITEADDITIONALNUMBERSTRINGPARAMS {
  HUICCAPP                            hUiccApp;
  RILPHONEBOOKADDITIONALNUMBERSTRING  RilPBANS;
} RILWRITEADDITIONALNUMBERSTRINGPARAMS, RILWRITEADDITIONALNUMBERSTRINGPARAMS;
````

## Members


`hUiccApp`



`RilPBANS`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |