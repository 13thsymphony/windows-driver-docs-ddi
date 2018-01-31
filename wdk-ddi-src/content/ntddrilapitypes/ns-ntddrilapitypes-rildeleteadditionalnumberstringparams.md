---
UID : NS:ntddrilapitypes.RILDELETEADDITIONALNUMBERSTRINGPARAMS
title : RILDELETEADDITIONALNUMBERSTRINGPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rildeleteadditionalnumberstringparams.htm
old-project : netvista
ms.assetid : 89ae70b9-56d9-4169-8bbd-0eb2d916a928
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddrilapitypes/RILDELETEADDITIONALNUMBERSTRINGPARAMS, RILDELETEADDITIONALNUMBERSTRINGPARAMS, RILDELETEADDITIONALNUMBERSTRINGPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rildeleteadditionalnumberstringparams, *LPRILDELETEADDITIONALNUMBERSTRINGPARAMS
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
req.typenames : RILDELETEADDITIONALNUMBERSTRINGPARAMS, *LPRILDELETEADDITIONALNUMBERSTRINGPARAMS
---

# RILDELETEADDITIONALNUMBERSTRINGPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILDELETEADDITIONALNUMBERSTRINGPARAMS {
  HUICCAPP  hUiccApp;
  DWORD     dwNumId;
} RILDELETEADDITIONALNUMBERSTRINGPARAMS, RILDELETEADDITIONALNUMBERSTRINGPARAMS;
````

## Members


`dwNumId`



`hUiccApp`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |