---
UID : NS:ntddrilapitypes.RILEXECUTORSTATE
title : RILEXECUTORSTATE
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilexecutorstate.htm
old-project : netvista
ms.assetid : 3d820c24-6f07-4ba2-b2e3-f3c799c6a1ef
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILEXECUTORSTATE, *LPRILEXECUTORSTATE, RILEXECUTORSTATE structure [Network Drivers Starting with Windows Vista], netvista.rilexecutorstate, ntddrilapitypes/RILEXECUTORSTATE
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
req.typenames : "*LPRILEXECUTORSTATE, RILEXECUTORSTATE"
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
| **Header** | ntddrilapitypes.h |