---
UID : NS:bdatypes._BDA_STRING
title : _BDA_STRING
author : windows-driver-content
description : .
old-location : stream\bda_string.htm
old-project : stream
ms.assetid : 69E2090F-02A6-43FB-85CB-E482B9142645
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _BDA_STRING, BDA_STRING, *PBDA_STRING
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
req.alt-api : BDA_STRING
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
req.typenames : BDA_STRING, *PBDA_STRING
---

# _BDA_STRING structure


## Syntax
````
typedef struct _BDA_STRING {
  PBDARESULT lResult;
  ULONG      ulStringSize;
  BYTE       argbString[MIN_DIMENSION];
} BDA_STRING, *PBDA_STRING;
````

## Members

        
            `argbString`

            
        
            `lResult`

            
        
            `ulStringSize`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bdatypes.h |