---
UID : NS:ntddrilapitypes.RILEMERGENCYMODECONTROLPARAMS
title : RILEMERGENCYMODECONTROLPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilemergencymodecontrolparams.htm
old-project : netvista
ms.assetid : b25ecc96-1ed2-4d8f-8dc8-0fafe58eca24
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.rilemergencymodecontrolparams, *LPRILEMERGENCYMODECONTROLPARAMS, ntddrilapitypes/RILEMERGENCYMODECONTROLPARAMS, RILEMERGENCYMODECONTROLPARAMS, RILEMERGENCYMODECONTROLPARAMS structure [Network Drivers Starting with Windows Vista]
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
req.typenames : "*LPRILEMERGENCYMODECONTROLPARAMS, RILEMERGENCYMODECONTROLPARAMS"
---

# RILEMERGENCYMODECONTROLPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILEMERGENCYMODECONTROLPARAMS {
  DWORD                                 dwExecutor;
  RILEMERGENCYMODECONTROLPARAMSCONTROL  dwEmergencyModeControl;
} RILEMERGENCYMODECONTROLPARAMS, RILEMERGENCYMODECONTROLPARAMS;
````

## Members


`dwEmergencyModeControl`



`dwExecutor`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |