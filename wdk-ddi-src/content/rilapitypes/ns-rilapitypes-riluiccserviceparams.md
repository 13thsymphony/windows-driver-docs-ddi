---
UID : NS:rilapitypes.RILUICCSERVICEPARAMS
title : RILUICCSERVICEPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\riluiccserviceparams_2.htm
old-project : netvista
ms.assetid : 56fba38d-6c5f-4b75-98b6-213a42f47bbb
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILUICCSERVICEPARAMS structure [Network Drivers Starting with Windows Vista], rilapitypes/RILUICCSERVICEPARAMS, netvista.riluiccserviceparams_2, RILUICCSERVICEPARAMS, *LPRILUICCSERVICEPARAMS
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
req.typenames : "*LPRILUICCSERVICEPARAMS, RILUICCSERVICEPARAMS"
req.product : Windows 10 or later.
---

# RILUICCSERVICEPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCSERVICEPARAMS {
  RILUICCSERVICE         service;
  BOOL                   fHasLockVerification;
  RILUICCLOCKCREDENTIAL  lockCredential;
  BOOL                   fEnable;
} RILUICCSERVICEPARAMS, RILUICCSERVICEPARAMS;
````

## Members


`fEnable`



`fHasLockVerification`



`lockCredential`



`service`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |