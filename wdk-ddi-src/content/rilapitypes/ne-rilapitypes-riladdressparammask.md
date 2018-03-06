---
UID: NE:rilapitypes.RILADDRESSPARAMMASK
title: RILADDRESSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladdressparammask_2.htm
old-project: netvista
ms.assetid: a9eaf2ec-5224-48e3-837b-279c1a44da68
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILADDRESSPARAMMASK, RILADDRESSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_A_ADDRESS, RIL_PARAM_A_ALL, RIL_PARAM_A_NUMPLAN, RIL_PARAM_A_TYPE, netvista.riladdressparammask_2, rilapitypes/RILADDRESSPARAMMASK, rilapitypes/RIL_PARAM_A_ADDRESS, rilapitypes/RIL_PARAM_A_ALL, rilapitypes/RIL_PARAM_A_NUMPLAN, rilapitypes/RIL_PARAM_A_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILADDRESSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILADDRESSPARAMMASK
req.product: Windows 10 or later.
---

# RILADDRESSPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILADDRESSPARAMMASK { 
  RIL_PARAM_A_TYPE,
  RIL_PARAM_A_NUMPLAN,
  RIL_PARAM_A_ADDRESS,
  RIL_PARAM_A_ALL
} RILADDRESSPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_A_ADDRESS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_A_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_A_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_A_NUMPLAN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_A_TYPE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |