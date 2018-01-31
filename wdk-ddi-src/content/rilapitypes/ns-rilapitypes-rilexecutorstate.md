---
UID : NS:rilapitypes.RILEXECUTORSTATE
title : RILEXECUTORSTATE
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilexecutorstate_2.htm
old-project : netvista
ms.assetid : 1333c13b-5d39-4143-a7ab-8425528eb4c9
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.rilexecutorstate_2, RILEXECUTORSTATE, RILEXECUTORSTATE structure [Network Drivers Starting with Windows Vista], rilapitypes/RILEXECUTORSTATE, *LPRILEXECUTORSTATE
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
req.typenames : "*LPRILEXECUTORSTATE, RILEXECUTORSTATE"
req.product : Windows 10 or later.
---

# RILEXECUTORSTATE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILEXECUTORSTATE {
  DWORD  cbSize;
  DWORD  dwExecutor;
  DWORD  dwFlags;
} RILEXECUTORSTATE, RILEXECUTORSTATE;
````

## Members


`cbSize`



`dwExecutor`



`dwFlags`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |