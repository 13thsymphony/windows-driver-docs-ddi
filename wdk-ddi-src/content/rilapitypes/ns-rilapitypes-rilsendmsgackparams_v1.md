---
UID : NS:rilapitypes.RILSENDMSGACKPARAMS_V1
title : RILSENDMSGACKPARAMS_V1
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsendmsgackparams_v1_2.htm
old-project : netvista
ms.assetid : 6e1f0283-76de-4c21-8205-cab83250dfae
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILSENDMSGACKPARAMS_V1, RILSENDMSGACKPARAMS_V1 structure [Network Drivers Starting with Windows Vista], netvista.rilsendmsgackparams_v1_2, rilapitypes/RILSENDMSGACKPARAMS_V1
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
req.typenames : RILSENDMSGACKPARAMS_V1
req.product : Windows 10 or later.
---

# RILSENDMSGACKPARAMS_V1 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSENDMSGACKPARAMS_V1 {
  DWORD            cbSize;
  DWORD            dwExecutor;
  HUICCAPP         hUiccApp;
  DWORD            dwAckID;
  RILMSGACKSTATUS  dwMsgStatus;
} RILSENDMSGACKPARAMS_V1, RILSENDMSGACKPARAMS_V1;
````

## Members


`cbSize`



`dwAckID`



`dwExecutor`



`dwMsgStatus`



`hUiccApp`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |