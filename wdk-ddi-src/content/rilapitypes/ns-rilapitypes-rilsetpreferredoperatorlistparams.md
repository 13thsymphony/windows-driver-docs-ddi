---
UID : NS:rilapitypes.RILSETPREFERREDOPERATORLISTPARAMS
title : RILSETPREFERREDOPERATORLISTPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsetpreferredoperatorlistparams_2.htm
old-project : netvista
ms.assetid : ff498364-f9ea-437f-904b-170ba0df7826
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILSETPREFERREDOPERATORLISTPARAMS, *LPRILSETPREFERREDOPERATORLISTPARAMS, RILSETPREFERREDOPERATORLISTPARAMS
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
req.alt-api : RILSETPREFERREDOPERATORLISTPARAMS
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
req.typenames : "*LPRILSETPREFERREDOPERATORLISTPARAMS, RILSETPREFERREDOPERATORLISTPARAMS"
req.product : Windows 10 or later.
---

# RILSETPREFERREDOPERATORLISTPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSETPREFERREDOPERATORLISTPARAMS {
  HUICCAPP             hUiccApp;
  DWORD                dwPreferredListSize;
  RILOPERATORNAMES [1] PreferredList;
} RILSETPREFERREDOPERATORLISTPARAMS, RILSETPREFERREDOPERATORLISTPARAMS;
````

## Members

        
            `dwPreferredListSize`

            
        
            `hUiccApp`

            
        
            `PreferredList`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |