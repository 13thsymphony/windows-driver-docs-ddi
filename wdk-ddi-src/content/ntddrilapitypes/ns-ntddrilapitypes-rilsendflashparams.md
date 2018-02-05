---
UID : NS:ntddrilapitypes.RILSENDFLASHPARAMS
title : RILSENDFLASHPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsendflashparams.htm
old-project : netvista
ms.assetid : e45b8f47-4e46-4265-9c56-055e753eb6e6
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddrilapitypes/RILSENDFLASHPARAMS, RILSENDFLASHPARAMS structure [Network Drivers Starting with Windows Vista], RILSENDFLASHPARAMS, netvista.rilsendflashparams, *LPRILSENDFLASHPARAMS
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
req.typenames : RILSENDFLASHPARAMS, *LPRILSENDFLASHPARAMS
---

# RILSENDFLASHPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSENDFLASHPARAMS {
  DWORD       dwExecutor;
  RILADDRESS  raAddress;
} RILSENDFLASHPARAMS, RILSENDFLASHPARAMS;
````

## Members


`dwExecutor`



`raAddress`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |