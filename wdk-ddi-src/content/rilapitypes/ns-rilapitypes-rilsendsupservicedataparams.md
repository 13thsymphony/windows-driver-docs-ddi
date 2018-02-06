---
UID: NS:rilapitypes.RILSENDSUPSERVICEDATAPARAMS
title: RILSENDSUPSERVICEDATAPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendsupservicedataparams_2.htm
old-project: netvista
ms.assetid: de9c7d56-5b57-4809-b5cf-93234c934d55
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSENDSUPSERVICEDATAPARAMS, RILSENDSUPSERVICEDATAPARAMS structure [Network Drivers Starting with Windows Vista], rilapitypes/RILSENDSUPSERVICEDATAPARAMS, netvista.rilsendsupservicedataparams_2, *LPRILSENDSUPSERVICEDATAPARAMS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILSENDSUPSERVICEDATAPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILSENDSUPSERVICEDATAPARAMS, RILSENDSUPSERVICEDATAPARAMS"
req.product: Windows 10 or later.
---

# RILSENDSUPSERVICEDATAPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSENDSUPSERVICEDATAPARAMS {
  DWORD     dwExecutor;
  DWORD     dwDataSize;
  WCHAR [1] wszData;
} RILSENDSUPSERVICEDATAPARAMS, RILSENDSUPSERVICEDATAPARAMS;
````

## Members


`dwDataSize`



`dwExecutor`



`wszData`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |