---
UID : NS:rilapitypes.RILGETDEVICEINFOPARAMS
title : RILGETDEVICEINFOPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilgetdeviceinfoparams_2.htm
old-project : netvista
ms.assetid : f5cbf775-4d6e-462a-9707-11a311a729ef
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILGETDEVICEINFOPARAMS, RILGETDEVICEINFOPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILGETDEVICEINFOPARAMS, netvista.rilgetdeviceinfoparams_2, rilapitypes/RILGETDEVICEINFOPARAMS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : rilapitypes.h
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
req.typenames : "*LPRILGETDEVICEINFOPARAMS, RILGETDEVICEINFOPARAMS"
req.product : Windows 10 or later.
---

# RILGETDEVICEINFOPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILGETDEVICEINFOPARAMS {
  DWORD                 dwExecutor;
  RILDEVICEINFORMATION  dwId;
} RILGETDEVICEINFOPARAMS, RILGETDEVICEINFOPARAMS;
````

## Members


`dwExecutor`



`dwId`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |