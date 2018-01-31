---
UID : NS:ntddrilapitypes.RILSETEXECUTORCONFIGPARAMS
title : RILSETEXECUTORCONFIGPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsetexecutorconfigparams.htm
old-project : netvista
ms.assetid : de392c8c-3153-48e8-85ad-dc1a5ed2812c
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILSETEXECUTORCONFIGPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILSETEXECUTORCONFIGPARAMS, ntddrilapitypes/RILSETEXECUTORCONFIGPARAMS, netvista.rilsetexecutorconfigparams, RILSETEXECUTORCONFIGPARAMS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddrilapitypes.h
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
req.typenames : RILSETEXECUTORCONFIGPARAMS, *LPRILSETEXECUTORCONFIGPARAMS
---

# RILSETEXECUTORCONFIGPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSETEXECUTORCONFIGPARAMS {
  DWORD              dwExecutor;
  RILEXECUTORCONFIG  rilExecutorConfig;
} RILSETEXECUTORCONFIGPARAMS, RILSETEXECUTORCONFIGPARAMS;
````

## Members


`dwExecutor`



`rilExecutorConfig`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |