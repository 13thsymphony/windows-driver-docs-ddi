---
UID : NS:rilapitypes.RILPHONEBOOKADDITIONALNUMBER
title : RILPHONEBOOKADDITIONALNUMBER
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilphonebookadditionalnumber_2.htm
old-project : netvista
ms.assetid : 1f6cb182-f85d-4760-96ab-9bd473a08066
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILPHONEBOOKADDITIONALNUMBER, RILPHONEBOOKADDITIONALNUMBER, *LPRILPHONEBOOKADDITIONALNUMBER
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
req.alt-api : RILPHONEBOOKADDITIONALNUMBER
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
req.typenames : RILPHONEBOOKADDITIONALNUMBER, *LPRILPHONEBOOKADDITIONALNUMBER
req.product : Windows 10 or later.
---

# RILPHONEBOOKADDITIONALNUMBER structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPHONEBOOKADDITIONALNUMBER {
  DWORD       cbSize;
  DWORD       dwParams;
  RILADDRESS  raAddress;
  DWORD       dwNumId;
} RILPHONEBOOKADDITIONALNUMBER, RILPHONEBOOKADDITIONALNUMBER;
````

## Members

        
            `cbSize`

            
        
            `dwNumId`

            
        
            `dwParams`

            
        
            `raAddress`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |