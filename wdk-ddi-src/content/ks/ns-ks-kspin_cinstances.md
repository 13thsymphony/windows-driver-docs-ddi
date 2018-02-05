---
UID : NS:ks.KSPIN_CINSTANCES
title : KSPIN_CINSTANCES
author : windows-driver-content
description : "."
old-location : stream\kspin_cinstances.htm
old-project : stream
ms.assetid : 90C861C3-26E0-43C0-A4CA-FD5491995DAB
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ks/KSPIN_CINSTANCES, ks/PKSPIN_CINSTANCES, PKSPIN_CINSTANCES, KSPIN_CINSTANCES structure [Streaming Media Devices], KSPIN_CINSTANCES, PKSPIN_CINSTANCES structure pointer [Streaming Media Devices], stream.kspin_cinstances, *PKSPIN_CINSTANCES
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PKSPIN_CINSTANCES, KSPIN_CINSTANCES"
---

# KSPIN_CINSTANCES structure


## Syntax
````
typedef struct {
  ULONG PossibleCount;
  ULONG CurrentCount;
} KSPIN_CINSTANCES, *PKSPIN_CINSTANCES;
````

## Members


`CurrentCount`

Specifies the current number of pins the pin factory has instantiated on the filter.

`PossibleCount`

Specifies the maximum number of pins the pin factory can instantiate on the filter, or KSINTANCE_INDETERMINATE if there is no maximum.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h |