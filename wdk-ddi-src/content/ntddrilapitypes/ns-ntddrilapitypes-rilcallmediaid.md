---
UID: NS:ntddrilapitypes.RILCALLMEDIAID
title: RILCALLMEDIAID
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaid.htm
old-project: netvista
ms.assetid: de55805d-d5fe-47ea-832d-536d8a7ee257
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILCALLMEDIAID, RILCALLMEDIAID, RILCALLMEDIAID structure [Network Drivers Starting with Windows Vista], netvista.rilcallmediaid, ntddrilapitypes/RILCALLMEDIAID"
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
-	RILCALLMEDIAID
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIAID, *LPRILCALLMEDIAID
---

# RILCALLMEDIAID structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCALLMEDIAID {
  RILCALLMEDIATYPE  dwType;
  DWORD             dwID;
} RILCALLMEDIAID, RILCALLMEDIAID;
````

## Members


`dwID`



`dwType`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |