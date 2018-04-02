---
UID: NE:ntddrilapitypes.RILLOCATIONINFOPARAMMASK
title: RILLOCATIONINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rillocationinfoparammask.htm
old-project: netvista
ms.assetid: 3d681026-7ccb-4dcb-bed1-505c13089177
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILLOCATIONINFOPARAMMASK, RILLOCATIONINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_LU_ALL, RIL_PARAM_LU_CELLID, RIL_PARAM_LU_HUICCAPP, RIL_PARAM_LU_LAC, RIL_PARAM_LU_TAC, netvista.rillocationinfoparammask, ntddrilapitypes/RILLOCATIONINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_LU_ALL, ntddrilapitypes/RIL_PARAM_LU_CELLID, ntddrilapitypes/RIL_PARAM_LU_HUICCAPP, ntddrilapitypes/RIL_PARAM_LU_LAC, ntddrilapitypes/RIL_PARAM_LU_TAC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h
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
-	RILLOCATIONINFOPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILLOCATIONINFOPARAMMASK
---

# RILLOCATIONINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILLOCATIONINFOPARAMMASK {
  RIL_PARAM_LU_EXECUTOR  ,
  RIL_PARAM_LU_HUICCAPP  ,
  RIL_PARAM_LU_LAC       ,
  RIL_PARAM_LU_TAC       ,
  RIL_PARAM_LU_CELLID    ,
  RIL_PARAM_LU_ALL
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_LU_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_LU_HUICCAPP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_LU_LAC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_LU_TAC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_LU_CELLID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_LU_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |