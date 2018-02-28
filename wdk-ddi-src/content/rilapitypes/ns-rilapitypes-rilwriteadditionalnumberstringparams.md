---
UID: NS:rilapitypes.RILWRITEADDITIONALNUMBERSTRINGPARAMS
title: RILWRITEADDITIONALNUMBERSTRINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilwriteadditionalnumberstringparams_2.htm
old-project: netvista
ms.assetid: d68553ef-a343-4297-b3a3-718747da422d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILWRITEADDITIONALNUMBERSTRINGPARAMS, RILWRITEADDITIONALNUMBERSTRINGPARAMS, RILWRITEADDITIONALNUMBERSTRINGPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilwriteadditionalnumberstringparams_2, rilapitypes/RILWRITEADDITIONALNUMBERSTRINGPARAMS"
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
| **Header** | rilapitypes.h |