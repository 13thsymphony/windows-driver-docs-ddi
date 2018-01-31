---
UID : NS:rilapitypes.RILSETNOTIFICATIONFILTERSTATEPARAMS
title : RILSETNOTIFICATIONFILTERSTATEPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsetnotificationfilterstateparams_2.htm
old-project : netvista
ms.assetid : 87dc2ef3-047c-4255-832c-508b378ca412
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.rilsetnotificationfilterstateparams_2, RILSETNOTIFICATIONFILTERSTATEPARAMS, rilapitypes/RILSETNOTIFICATIONFILTERSTATEPARAMS, *LPRILSETNOTIFICATIONFILTERSTATEPARAMS, RILSETNOTIFICATIONFILTERSTATEPARAMS structure [Network Drivers Starting with Windows Vista]
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
req.typenames : "*LPRILSETNOTIFICATIONFILTERSTATEPARAMS, RILSETNOTIFICATIONFILTERSTATEPARAMS"
req.product : Windows 10 or later.
---

# RILSETNOTIFICATIONFILTERSTATEPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSETNOTIFICATIONFILTERSTATEPARAMS {
  DWORD  dwFilterMask;
  DWORD  dwFilterState;
} RILSETNOTIFICATIONFILTERSTATEPARAMS, RILSETNOTIFICATIONFILTERSTATEPARAMS;
````

## Members


`dwFilterMask`



`dwFilterState`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |