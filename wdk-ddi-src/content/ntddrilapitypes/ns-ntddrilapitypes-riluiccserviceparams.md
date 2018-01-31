---
UID : NS:ntddrilapitypes.RILUICCSERVICEPARAMS
title : RILUICCSERVICEPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\riluiccserviceparams.htm
old-project : netvista
ms.assetid : 0f43b2be-d371-42d8-825b-56362de05c5e
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.riluiccserviceparams, ntddrilapitypes/RILUICCSERVICEPARAMS, RILUICCSERVICEPARAMS structure [Network Drivers Starting with Windows Vista], RILUICCSERVICEPARAMS, *LPRILUICCSERVICEPARAMS
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
req.typenames : "*LPRILUICCSERVICEPARAMS, RILUICCSERVICEPARAMS"
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
| **Header** | ntddrilapitypes.h |