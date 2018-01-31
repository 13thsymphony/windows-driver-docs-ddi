---
UID : NS:ntddrilapitypes.RILMANAGECALLSPARAMS_V1
title : RILMANAGECALLSPARAMS_V1
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilmanagecallsparams_v1.htm
old-project : netvista
ms.assetid : 7e89e417-59aa-4bcd-a6a9-0eaaa6a7a776
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddrilapitypes/RILMANAGECALLSPARAMS_V1, *LPRILMANAGECALLSPARAMS_V1, netvista.rilmanagecallsparams_v1, RILMANAGECALLSPARAMS_V1, RILMANAGECALLSPARAMS_V1 structure [Network Drivers Starting with Windows Vista]
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
req.typenames : RILMANAGECALLSPARAMS_V1, *LPRILMANAGECALLSPARAMS_V1
---

# RILMANAGECALLSPARAMS_V1 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMANAGECALLSPARAMS_V1 {
  DWORD                       dwExecutor;
  RILMANAGECALLPARAMSCOMMAND  dwCommand;
  DWORD                       dwID;
} RILMANAGECALLSPARAMS_V1, RILMANAGECALLSPARAMS_V1;
````

## Members


`dwCommand`



`dwExecutor`



`dwID`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |