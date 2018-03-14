---
UID: NS:ntddrilapitypes.RILVERSIONPARAMS
title: RILVERSIONPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilversionparams.htm
old-project: netvista
ms.assetid: c6931cee-2b86-4bf8-9e9d-b04e2df9eb12
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILVERSIONPARAMS, RILVERSIONPARAMS, RILVERSIONPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilversionparams, ntddrilapitypes/RILVERSIONPARAMS"
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
-	RILVERSIONPARAMS
product: Windows
targetos: Windows
req.typenames: RILVERSIONPARAMS, *LPRILVERSIONPARAMS
---

# RILVERSIONPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILVERSIONPARAMS {
  WORD  Minor;
  WORD  Major;
} RILVERSIONPARAMS, RILVERSIONPARAMS;
````

## Members


`Major`



`Minor`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |