---
UID : NS:ntddrilapitypes.RILMSGMWISUMMARY
title : RILMSGMWISUMMARY
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilmsgmwisummary.htm
old-project : netvista
ms.assetid : 5a718c4d-21c9-4dfd-844a-0053a379196d
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILMSGMWISUMMARY, *LPRILMSGMWISUMMARY, RILMSGMWISUMMARY
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
req.alt-api : RILMSGMWISUMMARY
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
req.typenames : "*LPRILMSGMWISUMMARY, RILMSGMWISUMMARY"
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
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |