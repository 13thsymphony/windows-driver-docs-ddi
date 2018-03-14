---
UID: NS:rilapitypes.RILERRORDETAILS
title: RILERRORDETAILS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilerrordetails.htm
old-project: netvista
ms.assetid: 9c9aaece-5c16-40c4-a039-5e32541500f7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILERRORDETAILS, RILERRORDETAILS, RILERRORDETAILS structure [Network Drivers Starting with Windows Vista], netvista.rilerrordetails, ntddrilapitypes/RILERRORDETAILS"
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
-	RILERRORDETAILS
product: Windows
targetos: Windows
req.typenames: RILERRORDETAILS, *LPRILERRORDETAILS
req.product: Windows 10 or later.
---

# RILERRORDETAILS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILERRORDETAILS {
  DWORD    cbSize;
  DWORD    dwParams;
  HRESULT  hResult;
  DWORD    dw3gppCause;
} RILERRORDETAILS, RILERRORDETAILS;
````

## Members


`cbSize`



`dw3gppCause`



`dwParams`



`hResult`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |