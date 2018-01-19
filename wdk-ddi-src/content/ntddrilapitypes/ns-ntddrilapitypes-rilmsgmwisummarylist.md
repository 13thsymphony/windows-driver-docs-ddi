---
UID : NS:ntddrilapitypes.RILMSGMWISUMMARYLIST
title : RILMSGMWISUMMARYLIST
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilmsgmwisummarylist.htm
old-project : netvista
ms.assetid : b698f9df-5a67-4ddf-9956-21fbd4f6f385
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILMSGMWISUMMARYLIST, RILMSGMWISUMMARYLIST, *LPRILMSGMWISUMMARYLIST
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
req.alt-api : RILMSGMWISUMMARYLIST
req.alt-loc : ntddrilapitypes.h
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
req.typenames : RILMSGMWISUMMARYLIST, *LPRILMSGMWISUMMARYLIST
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
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |