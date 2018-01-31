---
UID : NS:ntddrilapitypes.RILGETCALLFORWARDINGPARAMS
title : RILGETCALLFORWARDINGPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilgetcallforwardingparams.htm
old-project : netvista
ms.assetid : 94e24172-a149-4e74-9600-2fcb7396ef34
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddrilapitypes/RILGETCALLFORWARDINGPARAMS, RILGETCALLFORWARDINGPARAMS, netvista.rilgetcallforwardingparams, RILGETCALLFORWARDINGPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILGETCALLFORWARDINGPARAMS
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
req.typenames : "*LPRILGETCALLFORWARDINGPARAMS, RILGETCALLFORWARDINGPARAMS"
---

# RILGETCALLFORWARDINGPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILGETCALLFORWARDINGPARAMS {
  DWORD                            dwExecutor;
  RILCALLFORWARDINGSETTINGSREASON  dwReason;
  BOOL                             fAllClasses;
  DWORD                            dwInfoClasses;
} RILGETCALLFORWARDINGPARAMS, RILGETCALLFORWARDINGPARAMS;
````

## Members


`dwExecutor`



`dwInfoClasses`



`dwReason`



`fAllClasses`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |