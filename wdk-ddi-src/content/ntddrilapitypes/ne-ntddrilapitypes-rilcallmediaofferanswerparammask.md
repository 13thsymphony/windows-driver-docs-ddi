---
UID: NE:ntddrilapitypes.RILCALLMEDIAOFFERANSWERPARAMMASK
title: RILCALLMEDIAOFFERANSWERPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaofferanswerparammask.htm
old-project: netvista
ms.assetid: d11eb8f7-b670-45f3-8f90-6ea4db19bb20
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILCALLMEDIAOFFERANSWERPARAMMASK, RILCALLMEDIAOFFERANSWERPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_CMOA_ACTION, RIL_PARAM_CMOA_ALL, RIL_PARAM_CMOA_CHANGE, RIL_PARAM_CMOA_NEW_STATE, RIL_PARAM_CMOA_OLD_STATE, netvista.rilcallmediaofferanswerparammask, ntddrilapitypes/RILCALLMEDIAOFFERANSWERPARAMMASK, ntddrilapitypes/RIL_PARAM_CMOA_ACTION, ntddrilapitypes/RIL_PARAM_CMOA_ALL, ntddrilapitypes/RIL_PARAM_CMOA_CHANGE, ntddrilapitypes/RIL_PARAM_CMOA_NEW_STATE, ntddrilapitypes/RIL_PARAM_CMOA_OLD_STATE
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
-	RILCALLMEDIAOFFERANSWERPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIAOFFERANSWERPARAMMASK
---

# RILCALLMEDIAOFFERANSWERPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLMEDIAOFFERANSWERPARAMMASK { 
  RIL_PARAM_CMOA_CHANGE,
  RIL_PARAM_CMOA_ACTION,
  RIL_PARAM_CMOA_OLD_STATE,
  RIL_PARAM_CMOA_NEW_STATE,
  RIL_PARAM_CMOA_ALL
} RILCALLMEDIAOFFERANSWERPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_CMOA_ACTION</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CMOA_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CMOA_CHANGE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CMOA_ID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CMOA_NEW_STATE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CMOA_OLD_STATE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |