---
UID : NS:ntddrilapitypes.RILSENDRESTRICTEDUICCCMDPARAMS
title : RILSENDRESTRICTEDUICCCMDPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsendrestricteduicccmdparams.htm
old-project : netvista
ms.assetid : 22c7ae24-c2dc-46d6-b3c2-b908ad6d181c
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddrilapitypes/RILSENDRESTRICTEDUICCCMDPARAMS, RILSENDRESTRICTEDUICCCMDPARAMS, RILSENDRESTRICTEDUICCCMDPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsendrestricteduicccmdparams, *LPRILSENDRESTRICTEDUICCCMDPARAMS
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
req.typenames : "*LPRILSENDRESTRICTEDUICCCMDPARAMS, RILSENDRESTRICTEDUICCCMDPARAMS"
---

# RILSENDRESTRICTEDUICCCMDPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSENDRESTRICTEDUICCCMDPARAMS {
  DWORD                  cbSize;
  RILUICCCOMMAND         dwCommand;
  RILUICCCMDPARAMETERS   rscpParameters;
  BOOL                   fHasLockVerification;
  RILUICCLOCKCREDENTIAL  lockVerification;
  DWORD                  dwDataSize;
  BYTE [1]               pbData;
} RILSENDRESTRICTEDUICCCMDPARAMS, RILSENDRESTRICTEDUICCCMDPARAMS;
````

## Members


`cbSize`



`dwCommand`



`dwDataSize`



`fHasLockVerification`



`lockVerification`



`pbData`



`rscpParameters`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |