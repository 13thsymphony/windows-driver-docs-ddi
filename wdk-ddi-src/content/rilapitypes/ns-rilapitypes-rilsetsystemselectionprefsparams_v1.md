---
UID : NS:rilapitypes.RILSETSYSTEMSELECTIONPREFSPARAMS_V1
title : RILSETSYSTEMSELECTIONPREFSPARAMS_V1
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsetsystemselectionprefsparams_v1_2.htm
old-project : netvista
ms.assetid : 84e21a8a-f393-415a-87b6-48700044c9a9
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILSETSYSTEMSELECTIONPREFSPARAMS_V1, rilapitypes/RILSETSYSTEMSELECTIONPREFSPARAMS_V1, *LPRILSETSYSTEMSELECTIONPREFSPARAMS_V1, netvista.rilsetsystemselectionprefsparams_v1_2, RILSETSYSTEMSELECTIONPREFSPARAMS_V1 structure [Network Drivers Starting with Windows Vista]
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
req.typenames : RILSETSYSTEMSELECTIONPREFSPARAMS_V1, *LPRILSETSYSTEMSELECTIONPREFSPARAMS_V1
req.product : Windows 10 or later.
---

# RILSETSYSTEMSELECTIONPREFSPARAMS_V1 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSETSYSTEMSELECTIONPREFSPARAMS_V1 {
  DWORD                       dwFlags;
  RILSYSTEMSELECTIONPREFS_V1  rilSystemSelectionPrefs;
} RILSETSYSTEMSELECTIONPREFSPARAMS_V1, RILSETSYSTEMSELECTIONPREFSPARAMS_V1;
````

## Members


`dwFlags`



`rilSystemSelectionPrefs`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |