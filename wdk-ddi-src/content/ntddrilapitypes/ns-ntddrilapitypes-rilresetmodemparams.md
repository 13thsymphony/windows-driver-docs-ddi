---
UID : NS:ntddrilapitypes.RILRESETMODEMPARAMS
title : RILRESETMODEMPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilresetmodemparams.htm
old-project : netvista
ms.assetid : 6fde91f1-375e-4eaa-af48-67099b3e3227
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILRESETMODEMPARAMS, RILRESETMODEMPARAMS, *LPRILRESETMODEMPARAMS
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
req.alt-api : RILRESETMODEMPARAMS
req.alt-loc : ntddrilapitypes.h
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
req.typenames : RILRESETMODEMPARAMS, *LPRILRESETMODEMPARAMS
---

# RILRESETMODEMPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILRESETMODEMPARAMS {
  DWORD                       dwResetKind;
  DWORD                       dwNumberOfConfigItems;
  RILRESETMODEMCONFIGITEM [1] rmciModemConfigItems;
} RILRESETMODEMPARAMS, RILRESETMODEMPARAMS;
````

## Members

        
            `dwNumberOfConfigItems`

            
        
            `dwResetKind`

            
        
            `rmciModemConfigItems`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |