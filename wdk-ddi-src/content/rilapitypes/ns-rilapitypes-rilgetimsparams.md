---
UID : NS:rilapitypes.RILGETIMSPARAMS
title : RILGETIMSPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilgetimsparams_2.htm
old-project : netvista
ms.assetid : fc2b7e6f-3646-40a6-bdad-a1bbb94adf09
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILGETIMSPARAMS structure [Network Drivers Starting with Windows Vista], rilapitypes/RILGETIMSPARAMS, RILGETIMSPARAMS, *LPRILGETIMSPARAMS, netvista.rilgetimsparams_2
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
req.typenames : "*LPRILGETIMSPARAMS, RILGETIMSPARAMS"
req.product : Windows 10 or later.
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
| **Header** | rilapitypes.h |