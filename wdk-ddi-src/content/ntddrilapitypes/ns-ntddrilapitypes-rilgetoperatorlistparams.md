---
UID : NS:ntddrilapitypes.RILGETOPERATORLISTPARAMS
title : RILGETOPERATORLISTPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilgetoperatorlistparams.htm
old-project : netvista
ms.assetid : 75c8b3b3-4f33-465a-a35c-9d3056a2eb75
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.rilgetoperatorlistparams, RILGETOPERATORLISTPARAMS, RILGETOPERATORLISTPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILGETOPERATORLISTPARAMS, ntddrilapitypes/RILGETOPERATORLISTPARAMS
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
req.typenames : "*LPRILGETOPERATORLISTPARAMS, RILGETOPERATORLISTPARAMS"
---

# RILGETOPERATORLISTPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILGETOPERATORLISTPARAMS {
  DWORD  dwExecutor;
  DWORD  dwSystemTypes;
} RILGETOPERATORLISTPARAMS, RILGETOPERATORLISTPARAMS;
````

## Members


`dwExecutor`



`dwSystemTypes`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |