---
UID: NS:rilapitypes.RILCALLMEDIAID
title: RILCALLMEDIAID
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaid_2.htm
old-project: netvista
ms.assetid: ad367969-217c-4b9a-b9b1-1b6d1bf04f2e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILCALLMEDIAID, RILCALLMEDIAID, RILCALLMEDIAID structure [Network Drivers Starting with Windows Vista], netvista.rilcallmediaid_2, rilapitypes/RILCALLMEDIAID"
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
-	RILCALLMEDIAID
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIAID, *LPRILCALLMEDIAID
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |