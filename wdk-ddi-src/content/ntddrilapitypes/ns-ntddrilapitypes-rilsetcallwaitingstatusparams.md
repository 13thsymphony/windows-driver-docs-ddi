---
UID : NS:ntddrilapitypes.RILSETCALLWAITINGSTATUSPARAMS
title : RILSETCALLWAITINGSTATUSPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsetcallwaitingstatusparams.htm
old-project : netvista
ms.assetid : 1ba8d745-96bf-4d9d-8784-e6594360c632
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : "*LPRILSETCALLWAITINGSTATUSPARAMS, RILSETCALLWAITINGSTATUSPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsetcallwaitingstatusparams, ntddrilapitypes/RILSETCALLWAITINGSTATUSPARAMS, RILSETCALLWAITINGSTATUSPARAMS"
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
req.typenames : "*LPRILSETCALLWAITINGSTATUSPARAMS, RILSETCALLWAITINGSTATUSPARAMS"
---

# RILSETCALLWAITINGSTATUSPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSETCALLWAITINGSTATUSPARAMS {
  DWORD                     dwExecutor;
  BOOL                      fAllClasses;
  DWORD                     dwInfoClasses;
  RILSERVICESETTINGSSTATUS  dwStatus;
} RILSETCALLWAITINGSTATUSPARAMS, RILSETCALLWAITINGSTATUSPARAMS;
````

## Members


`dwExecutor`



`dwInfoClasses`



`dwStatus`



`fAllClasses`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |