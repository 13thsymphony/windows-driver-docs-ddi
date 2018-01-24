---
UID : NS:windot11.DOT11_CHANNEL_HINT
title : DOT11_CHANNEL_HINT
author : windows-driver-content
description : The DOT11_CHANNEL_HINT structure describes suggested channel numbers for an NLO operation.
old-location : netvista\dot11_channel_hint.htm
old-project : netvista
ms.assetid : B3E395C3-C642-4A5E-9005-88323A80F90E
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : DOT11_CHANNEL_HINT, *PDOT11_CHANNEL_HINT, DOT11_CHANNEL_HINT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : windot11.h
req.include-header : Windot11.h
req.target-type : Windows
req.target-min-winverclnt : Supported in Windows 8
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DOT11_CHANNEL_HINT
req.alt-loc : Windot11.h
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
req.typenames : "*PDOT11_CHANNEL_HINT, DOT11_CHANNEL_HINT"
req.product : Windows 10 or later.
---

# DOT11_CHANNEL_HINT structure


## Syntax
````
typedef struct _DOT11_CHANNEL_HINT {
  DOT11_PHY_TYPE Dot11PhyType;
  ULONG          uChannelNumber;
} DOT11_CHANNEL_HINT, *PDOT11_CHANNEL_HINT;
````

## Members

        
            `Dot11PhyType`

            The 802.11 PHY and media type.
        
            `uChannelNumber`

            Channel number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | windot11.h (include Windot11.h) |