---
UID: NS:rilapitypes.RILMSGMWISUMMARY
title: RILMSGMWISUMMARY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwisummary_2.htm
old-project: netvista
ms.assetid: 809373c0-210e-4947-a92f-a945b7846da7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILMSGMWISUMMARY, RILMSGMWISUMMARY, RILMSGMWISUMMARY structure [Network Drivers Starting with Windows Vista], netvista.rilmsgmwisummary_2, rilapitypes/RILMSGMWISUMMARY"
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
-	RILMSGMWISUMMARY
product: Windows
targetos: Windows
req.typenames: RILMSGMWISUMMARY, *LPRILMSGMWISUMMARY
req.product: Windows 10 or later.
---

# RILMSGMWISUMMARY structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMSGMWISUMMARY {
  RILMSGMWITYPE  dwMwiType;
  DWORD          dwNumberOfNewMessages;
  DWORD          dwNumberOfOldMessages;
  DWORD          dwNumberOfNewUrgentMessages;
  DWORD          dwNumberOfOldUrgentMessages;
} RILMSGMWISUMMARY, RILMSGMWISUMMARY;
````

## Members


`dwMwiType`



`dwNumberOfNewMessages`



`dwNumberOfNewUrgentMessages`



`dwNumberOfOldMessages`



`dwNumberOfOldUrgentMessages`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |