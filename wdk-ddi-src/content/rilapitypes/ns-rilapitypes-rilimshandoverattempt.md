---
UID: NS:rilapitypes.RILIMSHANDOVERATTEMPT
title: RILIMSHANDOVERATTEMPT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimshandoverattempt_2.htm
old-project: netvista
ms.assetid: de56a241-10a3-4f9c-970c-433ab997612d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILIMSHANDOVERATTEMPT, RILIMSHANDOVERATTEMPT, RILIMSHANDOVERATTEMPT structure [Network Drivers Starting with Windows Vista], netvista.rilimshandoverattempt_2, rilapitypes/RILIMSHANDOVERATTEMPT"
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
-	RILIMSHANDOVERATTEMPT
product: Windows
targetos: Windows
req.typenames: RILIMSHANDOVERATTEMPT, *LPRILIMSHANDOVERATTEMPT
req.product: Windows 10 or later.
---

# RILIMSHANDOVERATTEMPT structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILIMSHANDOVERATTEMPT {
  DWORD             cbSize;
  RILIMSSYSTEMTYPE  dwOldSystemType;
  RILIMSSYSTEMTYPE  dwDestSystemType;
  HRESULT           hrHandOverResult;
} RILIMSHANDOVERATTEMPT, RILIMSHANDOVERATTEMPT;
````

## Members


`cbSize`



`dwDestSystemType`



`dwOldSystemType`



`hrHandOverResult`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |