---
UID: NS:rilapitypes.RILMSGMWISUMMARYLIST
title: RILMSGMWISUMMARYLIST
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwisummarylist.htm
old-project: netvista
ms.assetid: b698f9df-5a67-4ddf-9956-21fbd4f6f385
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILMSGMWISUMMARYLIST, RILMSGMWISUMMARYLIST, RILMSGMWISUMMARYLIST structure [Network Drivers Starting with Windows Vista], netvista.rilmsgmwisummarylist, ntddrilapitypes/RILMSGMWISUMMARYLIST"
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
-	RILMSGMWISUMMARYLIST
product: Windows
targetos: Windows
req.typenames: RILMSGMWISUMMARYLIST, *LPRILMSGMWISUMMARYLIST
req.product: Windows 10 or later.
---

# RILMSGMWISUMMARYLIST structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILMSGMWISUMMARYLIST {
  DWORD            cbSize;
  DWORD            dwParams;
  DWORD            dwExecutor;
  DWORD            dwReferenceNumber;
  RILADDRESS       stAccountAddress;
  DWORD            dwTotalNumberOfDetailItems;
  DWORD            dwNumberOfSummaryItems;
  RILMSGMWISUMMARY stMwiSummary[1];
}  *LPRILMSGMWISUMMARYLIST;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`dwReferenceNumber`



`stAccountAddress`



`dwTotalNumberOfDetailItems`



`dwNumberOfSummaryItems`



`stMwiSummary`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |