---
UID: NE:ntddrilapitypes.RILUICCAPPPERSOCHECKSTATUSPARAMMASK
title: RILUICCAPPPERSOCHECKSTATUSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccapppersocheckstatusparammask.htm
old-project: netvista
ms.assetid: 552c6ee9-47e7-4863-95bb-256057a99649
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILUICCAPPPERSOCHECKSTATUSPARAMMASK, RILUICCAPPPERSOCHECKSTATUSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_UAPCS_ALL, RIL_PARAM_UAPCS_PERSOCHECKSTATE, RIL_PARAM_UAPCS_PERSOFEATURE, netvista.riluiccapppersocheckstatusparammask, ntddrilapitypes/RILUICCAPPPERSOCHECKSTATUSPARAMMASK, ntddrilapitypes/RIL_PARAM_UAPCS_ALL, ntddrilapitypes/RIL_PARAM_UAPCS_PERSOCHECKSTATE, ntddrilapitypes/RIL_PARAM_UAPCS_PERSOFEATURE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILUICCAPPPERSOCHECKSTATUSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUICCAPPPERSOCHECKSTATUSPARAMMASK
---

# RILUICCAPPPERSOCHECKSTATUSPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUICCAPPPERSOCHECKSTATUSPARAMMASK { 
  RIL_PARAM_UAPCS_PERSOFEATURE,
  RIL_PARAM_UAPCS_PERSOCHECKSTATE,
  RIL_PARAM_UAPCS_ALL
} RILUICCAPPPERSOCHECKSTATUSPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_UAPCS_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UAPCS_HUICCAPP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UAPCS_PERSOCHECKSTATE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UAPCS_PERSOFEATURE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |