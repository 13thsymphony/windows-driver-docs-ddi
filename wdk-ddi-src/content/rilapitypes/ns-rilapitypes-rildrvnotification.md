---
UID: NS:rilapitypes.RILDRVNOTIFICATION
title: RILDRVNOTIFICATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildrvnotification.htm
old-project: netvista
ms.assetid: 15567aae-a8ab-4289-9dd7-5bf7df80bfc9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILDRVNOTIFICATION, RILDRVNOTIFICATION, RILDRVNOTIFICATION structure [Network Drivers Starting with Windows Vista], netvista.rildrvnotification, ntddrilapitypes/RILDRVNOTIFICATION"
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
-	RILDRVNOTIFICATION
product: Windows
targetos: Windows
req.typenames: RILDRVNOTIFICATION, *LPRILDRVNOTIFICATION
req.product: Windows 10 or later.
---

# RILDRVNOTIFICATION structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILDRVNOTIFICATION {
  DWORD    cbSize;
  DWORD    cbSizeNeeded;
  DWORD    dwCode;
  HRESULT  hrCmdID;
  DWORD    dwDataSize;
  BYTE [1] pbData;
} RILDRVNOTIFICATION, RILDRVNOTIFICATION;
````

## Members


`cbSize`



`cbSizeNeeded`



`dwCode`



`hrCmdID`



`dwDataSize`



`pbData`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |