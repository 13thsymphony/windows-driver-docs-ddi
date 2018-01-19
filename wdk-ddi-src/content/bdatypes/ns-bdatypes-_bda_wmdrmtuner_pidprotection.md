---
UID : NS:bdatypes._BDA_WMDRMTUNER_PIDPROTECTION
title : _BDA_WMDRMTUNER_PIDPROTECTION
author : windows-driver-content
description : .
old-location : stream\bda_wmdrmtuner_pidprotection.htm
old-project : stream
ms.assetid : EA2590B0-7EF0-4E5E-A270-A13047BE0F2C
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _BDA_WMDRMTUNER_PIDPROTECTION, BDA_WMDRMTUNER_PIDPROTECTION, *PBDA_WMDRMTUNER_PIDPROTECTION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bdatypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : BDA_WMDRMTUNER_PIDPROTECTION
req.alt-loc : Bdatypes.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : BDA_WMDRMTUNER_PIDPROTECTION, *PBDA_WMDRMTUNER_PIDPROTECTION
---

# _BDA_WMDRMTUNER_PIDPROTECTION structure


## Syntax
````
typedef struct _BDA_WMDRMTUNER_PIDPROTECTION {
  PBDARESULT lResult;
  GUID       uuidKeyID;
} BDA_WMDRMTUNER_PIDPROTECTION, *PBDA_WMDRMTUNER_PIDPROTECTION;
````

## Members

        
            `lResult`

            
        
            `uuidKeyID`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bdatypes.h |