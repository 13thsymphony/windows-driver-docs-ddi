---
UID : NS:rilapitypes.RILSETSYSTEMSELECTIONPREFSPARAMS_V2
title : RILSETSYSTEMSELECTIONPREFSPARAMS_V2
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsetsystemselectionprefsparams_v2_2.htm
old-project : netvista
ms.assetid : d6284633-1f56-412c-a97a-b6c740129cce
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : "*LPRILSETSYSTEMSELECTIONPREFSPARAMS, RILSETSYSTEMSELECTIONPREFSPARAMS_V2 structure [Network Drivers Starting with Windows Vista], rilapitypes/RILSETSYSTEMSELECTIONPREFSPARAMS_V2, RILSETSYSTEMSELECTIONPREFSPARAMS, *LPRILSETSYSTEMSELECTIONPREFSPARAMS_V2, netvista.rilsetsystemselectionprefsparams_v2_2, RILSETSYSTEMSELECTIONPREFSPARAMS_V2"
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
req.typenames : RILSETSYSTEMSELECTIONPREFSPARAMS_V2, *LPRILSETSYSTEMSELECTIONPREFSPARAMS_V2, RILSETSYSTEMSELECTIONPREFSPARAMS, *LPRILSETSYSTEMSELECTIONPREFSPARAMS
req.product : Windows 10 or later.
---

# RILSETSYSTEMSELECTIONPREFSPARAMS_V2 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSETSYSTEMSELECTIONPREFSPARAMS_V2 {
  DWORD                    dwFlags;
  RILSYSTEMSELECTIONPREFS  rilSystemSelectionPrefs;
} RILSETSYSTEMSELECTIONPREFSPARAMS_V2, RILSETSYSTEMSELECTIONPREFSPARAMS_V2;
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