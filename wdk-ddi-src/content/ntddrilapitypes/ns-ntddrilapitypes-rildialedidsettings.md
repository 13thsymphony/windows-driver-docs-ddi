---
UID : NS:ntddrilapitypes.RILDIALEDIDSETTINGS
title : RILDIALEDIDSETTINGS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rildialedidsettings.htm
old-project : netvista
ms.assetid : e68ed118-76c7-44ff-a10f-dc64f1ce2d0e
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILDIALEDIDSETTINGS, *LPRILDIALEDIDSETTINGS, RILDIALEDIDSETTINGS
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
req.alt-api : RILDIALEDIDSETTINGS
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
req.typenames : "*LPRILDIALEDIDSETTINGS, RILDIALEDIDSETTINGS"
---

# RILDIALEDIDSETTINGS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILDIALEDIDSETTINGS {
  DWORD                         cbSize;
  DWORD                         dwParams;
  DWORD                         dwExecutor;
  RILSERVICESETTINGSSTATUS      dwStatus;
  RILSERVICEPROVISIONINGSTATUS  dwProvisioning;
} RILDIALEDIDSETTINGS, RILDIALEDIDSETTINGS;
````

## Members

        
            `cbSize`

            
        
            `dwExecutor`

            
        
            `dwParams`

            
        
            `dwProvisioning`

            
        
            `dwStatus`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |