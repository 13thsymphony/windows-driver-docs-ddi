---
UID : NS:bdatypes._BDA_DISEQC_SEND
title : _BDA_DISEQC_SEND
author : windows-driver-content
description : .
old-location : stream\bda_diseqc_send.htm
old-project : stream
ms.assetid : C40EAB5C-61AA-45FB-856E-07AB4D0228A6
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _BDA_DISEQC_SEND, BDA_DISEQC_SEND, *PBDA_DISEQC_SEND
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
req.alt-api : BDA_DISEQC_SEND
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
req.typenames : BDA_DISEQC_SEND, *PBDA_DISEQC_SEND
---

# _BDA_DISEQC_SEND structure


## Syntax
````
typedef struct _BDA_DISEQC_SEND {
  ULONG ulRequestId;
  ULONG ulPacketLength;
  BYTE  argbPacketData[8];
} BDA_DISEQC_SEND, *PBDA_DISEQC_SEND;
````

## Members

        
            `argbPacketData`

            
        
            `ulPacketLength`

            
        
            `ulRequestId`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bdatypes.h |