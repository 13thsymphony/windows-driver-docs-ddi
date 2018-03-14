---
UID: NS:rilapitypes.RILUICCSERVICE
title: RILUICCSERVICE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccservice.htm
old-project: netvista
ms.assetid: 67c8abef-c920-4bc4-8216-8b6026a1962d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILUICCSERVICE, RILUICCSERVICE, RILUICCSERVICE structure [Network Drivers Starting with Windows Vista], netvista.riluiccservice, ntddrilapitypes/RILUICCSERVICE"
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
-	RILUICCSERVICE
product: Windows
targetos: Windows
req.typenames: RILUICCSERVICE, *LPRILUICCSERVICE
req.product: Windows 10 or later.
---

# RILUICCSERVICE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCSERVICE {
  HUICCAPP               hUiccApp;
  RILUICCSERVICESERVICE  dwService;
} RILUICCSERVICE, RILUICCSERVICE;
````

## Members


`dwService`



`hUiccApp`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |