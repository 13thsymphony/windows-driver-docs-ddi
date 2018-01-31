---
UID : NS:1394._IRB_REQ_GET_GENERATION_COUNT
title : "_IRB_REQ_GET_GENERATION_COUNT"
author : windows-driver-content
description : This structure contains the fields necessary for the 1394 bus driver to carry out a GetGenerationCount request.
old-location : ieee\irb_req_get_generation_count.htm
old-project : IEEE
ms.assetid : C744C48E-476A-46F8-97BE-B3484E6FEF27
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : IEEE.irb_req_get_generation_count, IRB_REQ_GET_GENERATION_COUNT structure [Buses], IRB_REQ_GET_GENERATION_COUNT, 1394/IRB_REQ_GET_GENERATION_COUNT, _IRB_REQ_GET_GENERATION_COUNT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : 1394.h
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
req.typenames : IRB_REQ_GET_GENERATION_COUNT
---

# _IRB_REQ_GET_GENERATION_COUNT structure
This structure contains the fields necessary for the 1394 bus driver to carry out a GetGenerationCount request.

## Syntax
````
typedef struct _IRB_REQ_GET_GENERATION_COUNT {
  ULONG GenerationCount;
} IRB_REQ_GET_GENERATION_COUNT;
````

## Members


`GenerationCount`

Specifies the current generation count.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | 1394.h |