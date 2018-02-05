---
UID : NS:bdatypes._BDA_TUNER_DIAGNOSTICS
title : "_BDA_TUNER_DIAGNOSTICS"
author : windows-driver-content
description : "."
old-location : stream\bda_tuner_diagnostics.htm
old-project : stream
ms.assetid : 19AE53CF-7C09-4858-9D33-CF4B885111D3
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : PBDA_TUNER_DIAGNOSTICS, PBDA_TUNER_DIAGNOSTICS structure pointer [Streaming Media Devices], stream.bda_tuner_diagnostics, _BDA_TUNER_DIAGNOSTICS, BDA_TUNER_DIAGNOSTICS, bdatypes/BDA_TUNER_DIAGNOSTICS, *PBDA_TUNER_DIAGNOSTICS, bdatypes/PBDA_TUNER_DIAGNOSTICS, BDA_TUNER_DIAGNOSTICS structure [Streaming Media Devices]
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : BDA_TUNER_DIAGNOSTICS, *PBDA_TUNER_DIAGNOSTICS
---

# _BDA_TUNER_DIAGNOSTICS structure


## Syntax
````
typedef struct _BDA_TUNER_DIAGNOSTICS {
  PBDARESULT lResult;
  ULONG      ulSignalLevel;
  ULONG      ulSignalLevelQuality;
  ULONG      ulSignalNoiseRatio;
} BDA_TUNER_DIAGNOSTICS, *PBDA_TUNER_DIAGNOSTICS;
````

## Members


`lResult`



`ulSignalLevel`



`ulSignalLevelQuality`



`ulSignalNoiseRatio`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdatypes.h |