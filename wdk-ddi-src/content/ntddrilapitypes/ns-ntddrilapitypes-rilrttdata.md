---
UID : NS:ntddrilapitypes.RILRTTDATA
title : RILRTTDATA
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilrttdata.htm
old-project : netvista
ms.assetid : 037831c7-d0ef-4cbc-a414-a77010e228a5
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILRTTDATA, ntddrilapitypes/RILRTTDATA, netvista.rilrttdata, RILRTTDATA structure [Network Drivers Starting with Windows Vista], *LPRILRTTDATA
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
req.typenames : "*LPRILRTTDATA, RILRTTDATA"
---

# RILRTTDATA structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILRTTDATA {
  DWORD       cbSize;
  DWORD       dwID;
  DWORD       dwExecutor;
  WCHAR [127] wszRTTData;
} RILRTTDATA, RILRTTDATA;
````

## Members


`cbSize`



`dwExecutor`



`dwID`



`wszRTTData`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |