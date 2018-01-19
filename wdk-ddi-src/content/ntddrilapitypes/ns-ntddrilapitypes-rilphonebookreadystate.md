---
UID : NS:ntddrilapitypes.RILPHONEBOOKREADYSTATE
title : RILPHONEBOOKREADYSTATE
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilphonebookreadystate.htm
old-project : netvista
ms.assetid : cd71234b-4b46-4b7b-953b-32e6f014af03
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILPHONEBOOKREADYSTATE, *LPRILPHONEBOOKREADYSTATE, RILPHONEBOOKREADYSTATE
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
req.alt-api : RILPHONEBOOKREADYSTATE
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
req.typenames : "*LPRILPHONEBOOKREADYSTATE, RILPHONEBOOKREADYSTATE"
---

# RILPHONEBOOKREADYSTATE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPHONEBOOKREADYSTATE {
  DWORD     cbSize;
  HUICCAPP  hUiccApp;
  DWORD     dwStoreLocations;
} RILPHONEBOOKREADYSTATE, RILPHONEBOOKREADYSTATE;
````

## Members

        
            `cbSize`

            
        
            `dwStoreLocations`

            
        
            `hUiccApp`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |