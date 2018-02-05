---
UID : NS:ntddrilapitypes.RILSENDUICCTOOLKITCMDRESPONSEPARAMS
title : RILSENDUICCTOOLKITCMDRESPONSEPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsenduicctoolkitcmdresponseparams.htm
old-project : netvista
ms.assetid : 9006d542-0f83-4cd4-ab81-d2e4cce67406
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.rilsenduicctoolkitcmdresponseparams, RILSENDUICCTOOLKITCMDRESPONSEPARAMS structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILSENDUICCTOOLKITCMDRESPONSEPARAMS, RILSENDUICCTOOLKITCMDRESPONSEPARAMS, *LPRILSENDUICCTOOLKITCMDRESPONSEPARAMS
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
req.typenames : "*LPRILSENDUICCTOOLKITCMDRESPONSEPARAMS, RILSENDUICCTOOLKITCMDRESPONSEPARAMS"
---

# RILSENDUICCTOOLKITCMDRESPONSEPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSENDUICCTOOLKITCMDRESPONSEPARAMS {
  DWORD    dwSlotIndex;
  DWORD    dwDetailsSize;
  BYTE [1] bDetails;
} RILSENDUICCTOOLKITCMDRESPONSEPARAMS, RILSENDUICCTOOLKITCMDRESPONSEPARAMS;
````

## Members


`bDetails`



`dwDetailsSize`



`dwSlotIndex`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |