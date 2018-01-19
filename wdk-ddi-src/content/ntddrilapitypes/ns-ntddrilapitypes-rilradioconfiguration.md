---
UID : NS:ntddrilapitypes.RILRADIOCONFIGURATION
title : RILRADIOCONFIGURATION
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilradioconfiguration.htm
old-project : netvista
ms.assetid : 24ff04b3-aec2-4bce-aa85-e33f3dbffa22
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILRADIOCONFIGURATION, RILRADIOCONFIGURATION, *LPRILRADIOCONFIGURATION
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
req.alt-api : RILRADIOCONFIGURATION
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
req.typenames : RILRADIOCONFIGURATION, *LPRILRADIOCONFIGURATION
---

# RILRADIOCONFIGURATION structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILRADIOCONFIGURATION {
  DWORD                           dwConfigId;
  RILRADIOCONFIGURATIONRADIOTYPE  dwRadioType;
  DWORD [2]                       dwSystemTypes;
} RILRADIOCONFIGURATION, RILRADIOCONFIGURATION;
````

## Members

        
            `dwConfigId`

            
        
            `dwRadioType`

            
        
            `dwSystemTypes`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |