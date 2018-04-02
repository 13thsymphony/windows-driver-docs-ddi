---
UID: NE:rilapitypes.RILCALLFORWARDINGSETTINGSPARAMMASK
title: RILCALLFORWARDINGSETTINGSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallforwardingsettingsparammask.htm
old-project: netvista
ms.assetid: 0da4e19f-9e7b-4986-bdb1-fc59e177f3fa
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILCALLFORWARDINGSETTINGSPARAMMASK, RILCALLFORWARDINGSETTINGSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_CFS_ADDRESS, RIL_PARAM_CFS_ALL, RIL_PARAM_CFS_DELAYTIME, RIL_PARAM_CFS_INFOCLASSES, RIL_PARAM_CFS_SUBADDRESS, netvista.rilcallforwardingsettingsparammask, ntddrilapitypes/RILCALLFORWARDINGSETTINGSPARAMMASK, ntddrilapitypes/RIL_PARAM_CFS_ADDRESS, ntddrilapitypes/RIL_PARAM_CFS_ALL, ntddrilapitypes/RIL_PARAM_CFS_DELAYTIME, ntddrilapitypes/RIL_PARAM_CFS_INFOCLASSES, ntddrilapitypes/RIL_PARAM_CFS_SUBADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
-	RILCALLFORWARDINGSETTINGSPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILCALLFORWARDINGSETTINGSPARAMMASK
req.product: Windows 10 or later.
---

# RILCALLFORWARDINGSETTINGSPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILCALLFORWARDINGSETTINGSPARAMMASK {
  RIL_PARAM_CFS_STATUS       ,
  RIL_PARAM_CFS_INFOCLASSES  ,
  RIL_PARAM_CFS_ADDRESS      ,
  RIL_PARAM_CFS_SUBADDRESS   ,
  RIL_PARAM_CFS_DELAYTIME    ,
  RIL_PARAM_CFS_ALL
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_CFS_STATUS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CFS_INFOCLASSES</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CFS_ADDRESS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CFS_SUBADDRESS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CFS_DELAYTIME</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CFS_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |