---
UID : NS:ntddrilapitypes.RILGETPREFERREDOPERATORLISTPARAMS
title : RILGETPREFERREDOPERATORLISTPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilgetpreferredoperatorlistparams.htm
old-project : netvista
ms.assetid : b1cc3a45-cfd9-4a7f-94e7-bc5c0d2a4e80
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILGETPREFERREDOPERATORLISTPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILGETPREFERREDOPERATORLISTPARAMS, RILGETPREFERREDOPERATORLISTPARAMS, ntddrilapitypes/RILGETPREFERREDOPERATORLISTPARAMS, netvista.rilgetpreferredoperatorlistparams
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
req.typenames : RILGETPREFERREDOPERATORLISTPARAMS, *LPRILGETPREFERREDOPERATORLISTPARAMS
---

# RILGETPREFERREDOPERATORLISTPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILGETPREFERREDOPERATORLISTPARAMS {
  HUICCAPP                             hUiccApp;
  RILGETPREFERENCEDOPERATORLISTFORMAT  dwFormat;
} RILGETPREFERREDOPERATORLISTPARAMS, RILGETPREFERREDOPERATORLISTPARAMS;
````

## Members


`dwFormat`



`hUiccApp`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |