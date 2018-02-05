---
UID : NS:ntddrilapitypes.RILMSGMWISUMMARYLIST
title : RILMSGMWISUMMARYLIST
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilmsgmwisummarylist.htm
old-project : netvista
ms.assetid : b698f9df-5a67-4ddf-9956-21fbd4f6f385
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.rilmsgmwisummarylist, RILMSGMWISUMMARYLIST, *LPRILMSGMWISUMMARYLIST, ntddrilapitypes/RILMSGMWISUMMARYLIST, RILMSGMWISUMMARYLIST structure [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddrilapitypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*LPRILMSGMWISUMMARYLIST, RILMSGMWISUMMARYLIST"
---

# RILMSGMWISUMMARYLIST structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMSGMWISUMMARYLIST {
  DWORD                cbSize;
  DWORD                dwParams;
  DWORD                dwExecutor;
  DWORD                dwReferenceNumber;
  RILADDRESS           stAccountAddress;
  DWORD                dwTotalNumberOfDetailItems;
  DWORD                dwNumberOfSummaryItems;
  RILMSGMWISUMMARY [1] stMwiSummary;
} RILMSGMWISUMMARYLIST, RILMSGMWISUMMARYLIST;
````

## Members


`cbSize`



`dwExecutor`



`dwNumberOfSummaryItems`



`dwParams`



`dwReferenceNumber`



`dwTotalNumberOfDetailItems`



`stAccountAddress`



`stMwiSummary`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |