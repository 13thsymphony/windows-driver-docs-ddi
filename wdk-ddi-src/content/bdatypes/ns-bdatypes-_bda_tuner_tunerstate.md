---
UID : NS:bdatypes._BDA_TUNER_TUNERSTATE
title : _BDA_TUNER_TUNERSTATE
author : windows-driver-content
description : .
old-location : stream\bda_tuner_tunerstate.htm
old-project : stream
ms.assetid : 77B30ADC-27F2-4883-97FC-F6C29B539EE0
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : BDA_TUNER_TUNERSTATE structure [Streaming Media Devices], bdatypes/BDA_TUNER_TUNERSTATE, BDA_TUNER_TUNERSTATE, PBDA_TUNER_TUNERSTATE structure pointer [Streaming Media Devices], *PBDA_TUNER_TUNERSTATE, PBDA_TUNER_TUNERSTATE, stream.bda_tuner_tunerstate, _BDA_TUNER_TUNERSTATE, bdatypes/PBDA_TUNER_TUNERSTATE
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
req.typenames : BDA_TUNER_TUNERSTATE, *PBDA_TUNER_TUNERSTATE
---

# _BDA_TUNER_TUNERSTATE structure


## Syntax
````
typedef struct _BDA_TUNER_TUNERSTATE {
  PBDARESULT lResult;
  ULONG      ulTuneLength;
  BYTE       argbTuneData[MIN_DIMENSION];
} BDA_TUNER_TUNERSTATE, *PBDA_TUNER_TUNERSTATE;
````

## Members


`argbTuneData`



`lResult`



`ulTuneLength`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bdatypes.h |