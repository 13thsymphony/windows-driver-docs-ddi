---
UID: NS:rilapitypes.RILMANAGECALLSPARAMS_V1
title: RILMANAGECALLSPARAMS_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmanagecallsparams_v1.htm
old-project: netvista
ms.assetid: 7e89e417-59aa-4bcd-a6a9-0eaaa6a7a776
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILMANAGECALLSPARAMS_V1, RILMANAGECALLSPARAMS_V1, RILMANAGECALLSPARAMS_V1 structure [Network Drivers Starting with Windows Vista], netvista.rilmanagecallsparams_v1, ntddrilapitypes/RILMANAGECALLSPARAMS_V1"
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
-	RILMANAGECALLSPARAMS_V1
product: Windows
targetos: Windows
req.typenames: RILMANAGECALLSPARAMS_V1, *LPRILMANAGECALLSPARAMS_V1
req.product: Windows 10 or later.
---

# RILMANAGECALLSPARAMS_V1 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMANAGECALLSPARAMS_V1 {
  DWORD                       dwExecutor;
  RILMANAGECALLPARAMSCOMMAND  dwCommand;
  DWORD                       dwID;
} RILMANAGECALLSPARAMS_V1, RILMANAGECALLSPARAMS_V1;
````

## Members


`dwExecutor`



`dwCommand`



`dwID`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |