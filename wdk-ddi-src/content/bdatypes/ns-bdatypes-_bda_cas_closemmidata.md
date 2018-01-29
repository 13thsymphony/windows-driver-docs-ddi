---
UID : NS:bdatypes._BDA_CAS_CLOSEMMIDATA
title : _BDA_CAS_CLOSEMMIDATA
author : windows-driver-content
description : .
old-location : stream\bda_cas_closemmidata.htm
old-project : stream
ms.assetid : D1AA47FB-A419-4B25-89A8-7481630B108A
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : bdatypes/PBDA_CAS_CLOSEMMIDATA, stream.bda_cas_closemmidata, PBDA_CAS_CLOSEMMIDATA structure pointer [Streaming Media Devices], bdatypes/BDA_CAS_CLOSEMMIDATA, *PBDA_CAS_CLOSEMMIDATA, BDA_CAS_CLOSEMMIDATA, _BDA_CAS_CLOSEMMIDATA, PBDA_CAS_CLOSEMMIDATA, BDA_CAS_CLOSEMMIDATA structure [Streaming Media Devices]
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
req.typenames : "*PBDA_CAS_CLOSEMMIDATA, BDA_CAS_CLOSEMMIDATA"
---

# _BDA_CAS_CLOSEMMIDATA structure


## Syntax
````
typedef struct _BDA_CAS_CLOSEMMIDATA {
  ULONG ulDialogNumber;
} BDA_CAS_CLOSEMMIDATA, *PBDA_CAS_CLOSEMMIDATA;
````

## Members


`ulDialogNumber`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bdatypes.h |