---
UID : NS:rilapitypes.RILERRORDETAILS
title : RILERRORDETAILS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilerrordetails_2.htm
old-project : netvista
ms.assetid : decfcafa-fe8b-44f6-913b-c04cf3b320a3
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILERRORDETAILS, RILERRORDETAILS, *LPRILERRORDETAILS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : rilapitypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RILERRORDETAILS
req.alt-loc : rilapitypes.h
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
req.typenames : RILERRORDETAILS, *LPRILERRORDETAILS
req.product : Windows 10 or later.
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
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |