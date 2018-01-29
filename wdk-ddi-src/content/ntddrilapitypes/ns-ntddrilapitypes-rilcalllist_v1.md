---
UID : NS:ntddrilapitypes.RILCALLLIST_V1
title : RILCALLLIST_V1
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcalllist_v1.htm
old-project : netvista
ms.assetid : 09b4f4e7-2688-4d6e-8512-a94c5ce25a79
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.rilcalllist_v1, RILCALLLIST_V1, ntddrilapitypes/RILCALLLIST_V1, *LPRILCALLLIST_V1, RILCALLLIST_V1 structure [Network Drivers Starting with Windows Vista]
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
req.typenames : RILCALLLIST_V1, *LPRILCALLLIST_V1
---

# RILCALLLIST_V1 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCALLLIST_V1 {
  DWORD              dwNumberOfCalls;
  RILCALLINFO_V1 [1] rciCallInfo;
} RILCALLLIST_V1, RILCALLLIST_V1;
````

## Members


`dwNumberOfCalls`



`rciCallInfo`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |