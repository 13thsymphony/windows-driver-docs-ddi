---
UID : NS:rilapitypes.RILSENDSUPSERVICEDATARESPONSEPARAMS
title : RILSENDSUPSERVICEDATARESPONSEPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsendsupservicedataresponseparams_2.htm
old-project : netvista
ms.assetid : 2b5ac749-9097-43bf-a0e6-a18374f15a86
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : "*LPRILSENDSUPSERVICEDATARESPONSEPARAMS, netvista.rilsendsupservicedataresponseparams_2, RILSENDSUPSERVICEDATARESPONSEPARAMS structure [Network Drivers Starting with Windows Vista], RILSENDSUPSERVICEDATARESPONSEPARAMS, rilapitypes/RILSENDSUPSERVICEDATARESPONSEPARAMS"
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
req.typenames : RILSENDSUPSERVICEDATARESPONSEPARAMS, *LPRILSENDSUPSERVICEDATARESPONSEPARAMS
req.product : Windows 10 or later.
---

# RILSENDSUPSERVICEDATARESPONSEPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSENDSUPSERVICEDATARESPONSEPARAMS {
  DWORD     dwExecutor;
  DWORD     dwDataSize;
  WCHAR [1] wszData;
} RILSENDSUPSERVICEDATARESPONSEPARAMS, RILSENDSUPSERVICEDATARESPONSEPARAMS;
````

## Members


`dwDataSize`



`dwExecutor`



`wszData`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |