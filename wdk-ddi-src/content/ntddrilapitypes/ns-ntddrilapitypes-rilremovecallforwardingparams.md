---
UID : NS:ntddrilapitypes.RILREMOVECALLFORWARDINGPARAMS
title : RILREMOVECALLFORWARDINGPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilremovecallforwardingparams.htm
old-project : netvista
ms.assetid : f6eaaa56-8444-496b-8b14-63bb2368d6ba
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : "*LPRILREMOVECALLFORWARDINGPARAMS, RILREMOVECALLFORWARDINGPARAMS structure [Network Drivers Starting with Windows Vista], RILREMOVECALLFORWARDINGPARAMS, netvista.rilremovecallforwardingparams, ntddrilapitypes/RILREMOVECALLFORWARDINGPARAMS"
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
req.typenames : RILREMOVECALLFORWARDINGPARAMS, *LPRILREMOVECALLFORWARDINGPARAMS
---

# RILREMOVECALLFORWARDINGPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILREMOVECALLFORWARDINGPARAMS {
  DWORD                            dwExecutor;
  RILCALLFORWARDINGSETTINGSREASON  dwReason;
  DWORD                            dwInfoClasses;
} RILREMOVECALLFORWARDINGPARAMS, RILREMOVECALLFORWARDINGPARAMS;
````

## Members


`dwExecutor`



`dwInfoClasses`



`dwReason`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |