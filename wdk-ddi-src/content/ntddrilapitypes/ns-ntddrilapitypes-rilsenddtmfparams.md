---
UID : NS:ntddrilapitypes.RILSENDDTMFPARAMS
title : RILSENDDTMFPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsenddtmfparams.htm
old-project : netvista
ms.assetid : b08767f9-6b2d-4930-bd02-ebc89f2bdb7d
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILSENDDTMFPARAMS, RILSENDDTMFPARAMS, *LPRILSENDDTMFPARAMS
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
req.alt-api : RILSENDDTMFPARAMS
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
req.typenames : RILSENDDTMFPARAMS, *LPRILSENDDTMFPARAMS
---

# RILSENDDTMFPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSENDDTMFPARAMS {
  DWORD      dwExecutor;
  char [256] szDTMF;
  DWORD      dwDigitOnTimeMs;
  DWORD      dwDigitOffTimeMs;
} RILSENDDTMFPARAMS, RILSENDDTMFPARAMS;
````

## Members

        
            `dwDigitOffTimeMs`

            
        
            `dwDigitOnTimeMs`

            
        
            `dwExecutor`

            
        
            `szDTMF`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |