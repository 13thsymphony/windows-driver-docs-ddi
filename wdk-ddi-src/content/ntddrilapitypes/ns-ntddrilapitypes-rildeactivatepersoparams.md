---
UID : NS:ntddrilapitypes.RILDEACTIVATEPERSOPARAMS
title : RILDEACTIVATEPERSOPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rildeactivatepersoparams.htm
old-project : netvista
ms.assetid : 408ae5d4-f83f-4e4a-9850-a7bae70a2da2
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : "*LPRILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILDEACTIVATEPERSOPARAMS, netvista.rildeactivatepersoparams"
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
req.typenames : RILDEACTIVATEPERSOPARAMS, *LPRILDEACTIVATEPERSOPARAMS
---

# RILDEACTIVATEPERSOPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILDEACTIVATEPERSOPARAMS {
  DWORD      dwPersoFeature;
  char [256] szPassword;
} RILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS;
````

## Members


`dwPersoFeature`



`szPassword`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |