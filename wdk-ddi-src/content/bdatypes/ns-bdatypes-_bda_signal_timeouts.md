---
UID : NS:bdatypes._BDA_SIGNAL_TIMEOUTS
title : _BDA_SIGNAL_TIMEOUTS
author : windows-driver-content
description : .
old-location : stream\bda_signal_timeouts.htm
old-project : stream
ms.assetid : CFEF848D-8268-4FFC-A629-D122021D8411
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _BDA_SIGNAL_TIMEOUTS, *PBDA_SIGNAL_TIMEOUTS, BDA_SIGNAL_TIMEOUTS
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
req.alt-api : BDA_SIGNAL_TIMEOUTS
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
req.typenames : "*PBDA_SIGNAL_TIMEOUTS, BDA_SIGNAL_TIMEOUTS"
---

# _BDA_SIGNAL_TIMEOUTS structure


## Syntax
````
typedef struct _BDA_SIGNAL_TIMEOUTS {
  ULONG ulCarrierTimeoutMs;
  ULONG ulScanningTimeoutMs;
  ULONG ulTuningTimeoutMs;
} BDA_SIGNAL_TIMEOUTS, *PBDA_SIGNAL_TIMEOUTS;
````

## Members

        
            `ulCarrierTimeoutMs`

            
        
            `ulScanningTimeoutMs`

            
        
            `ulTuningTimeoutMs`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bdatypes.h |