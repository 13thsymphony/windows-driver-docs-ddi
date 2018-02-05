---
UID : NS:ntddrilapitypes.RILTERMINALCAPABILITYINFO
title : RILTERMINALCAPABILITYINFO
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilterminalcapabilityinfo.htm
old-project : netvista
ms.assetid : e6ad67bf-cd16-469e-af49-6a640a4319c0
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : "*LPRILTERMINALCAPABILITYINFO, netvista.rilterminalcapabilityinfo, RILTERMINALCAPABILITYINFO structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILTERMINALCAPABILITYINFO, RILTERMINALCAPABILITYINFO"
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
req.typenames : RILTERMINALCAPABILITYINFO, *LPRILTERMINALCAPABILITYINFO
---

# RILTERMINALCAPABILITYINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILTERMINALCAPABILITYINFO {
  DWORD      dwSize;
  BYTE [256] bData;
} RILTERMINALCAPABILITYINFO, RILTERMINALCAPABILITYINFO;
````

## Members


`bData`



`dwSize`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |