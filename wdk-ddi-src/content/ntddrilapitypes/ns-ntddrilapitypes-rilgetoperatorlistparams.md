---
UID: NS:ntddrilapitypes.RILGETOPERATORLISTPARAMS
title: RILGETOPERATORLISTPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetoperatorlistparams.htm
old-project: netvista
ms.assetid: 75c8b3b3-4f33-465a-a35c-9d3056a2eb75
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILGETOPERATORLISTPARAMS, RILGETOPERATORLISTPARAMS, RILGETOPERATORLISTPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilgetoperatorlistparams, ntddrilapitypes/RILGETOPERATORLISTPARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILGETOPERATORLISTPARAMS
product: Windows
targetos: Windows
req.typenames: RILGETOPERATORLISTPARAMS, *LPRILGETOPERATORLISTPARAMS
---

# RILGETOPERATORLISTPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILGETOPERATORLISTPARAMS {
  DWORD  dwExecutor;
  DWORD  dwSystemTypes;
} RILGETOPERATORLISTPARAMS, RILGETOPERATORLISTPARAMS;
````

## Members


`dwExecutor`



`dwSystemTypes`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |