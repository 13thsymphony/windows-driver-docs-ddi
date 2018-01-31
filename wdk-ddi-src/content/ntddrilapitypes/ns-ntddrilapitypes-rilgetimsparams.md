---
UID : NS:ntddrilapitypes.RILGETIMSPARAMS
title : RILGETIMSPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilgetimsparams.htm
old-project : netvista
ms.assetid : 4e8f01af-9279-483a-90f9-d0391122ba5b
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.rilgetimsparams, RILGETIMSPARAMS structure [Network Drivers Starting with Windows Vista], RILGETIMSPARAMS, *LPRILGETIMSPARAMS, ntddrilapitypes/RILGETIMSPARAMS
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
req.typenames : "*LPRILGETIMSPARAMS, RILGETIMSPARAMS"
---

# RILGETIMSPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILGETIMSPARAMS {
  DWORD  cbSize;
  DWORD  dwExecutor;
} RILGETIMSPARAMS, RILGETIMSPARAMS;
````

## Members


`cbSize`



`dwExecutor`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |