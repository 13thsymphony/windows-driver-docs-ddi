---
UID : NS:rilapitypes.RILDIALPARAMS_V2
title : RILDIALPARAMS_V2
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rildialparams_v2_2.htm
old-project : netvista
ms.assetid : ca42a4c3-1589-4434-8d76-59f877e1e664
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : rilapitypes/RILDIALPARAMS_V2, RILDIALPARAMS, RILDIALPARAMS_V2 structure [Network Drivers Starting with Windows Vista], *LPRILDIALPARAMS_V2, RILDIALPARAMS_V2, *LPRILDIALPARAMS, netvista.rildialparams_v2_2
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
req.typenames : RILDIALPARAMS, *LPRILDIALPARAMS_V2, *LPRILDIALPARAMS, RILDIALPARAMS_V2
req.product : Windows 10 or later.
---

# RILDIALPARAMS_V2 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILDIALPARAMS_V2 {
  DWORD                       dwExecutor;
  RILADDRESS                  raAddress;
  DWORD                       dwOptions;
  RILCALLTYPE                 dwType;
  BOOL                        fHasMediaOffer;
  RILCALLMEDIAOFFERANSWERSET  rcmMediaOffer;
} RILDIALPARAMS_V2, RILDIALPARAMS_V2;
````

## Members


`dwExecutor`



`dwOptions`



`dwType`



`fHasMediaOffer`



`raAddress`



`rcmMediaOffer`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |