---
UID : NS:bdatypes._BDA_WMDRMTUNER_PIDPROTECTION
title : "_BDA_WMDRMTUNER_PIDPROTECTION"
author : windows-driver-content
description : "."
old-location : stream\bda_wmdrmtuner_pidprotection.htm
old-project : stream
ms.assetid : EA2590B0-7EF0-4E5E-A270-A13047BE0F2C
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : BDA_WMDRMTUNER_PIDPROTECTION, bdatypes/BDA_WMDRMTUNER_PIDPROTECTION, bdatypes/PBDA_WMDRMTUNER_PIDPROTECTION, *PBDA_WMDRMTUNER_PIDPROTECTION, PBDA_WMDRMTUNER_PIDPROTECTION, BDA_WMDRMTUNER_PIDPROTECTION structure [Streaming Media Devices], _BDA_WMDRMTUNER_PIDPROTECTION, stream.bda_wmdrmtuner_pidprotection, PBDA_WMDRMTUNER_PIDPROTECTION structure pointer [Streaming Media Devices]
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
| **Header** | bdatypes.h |