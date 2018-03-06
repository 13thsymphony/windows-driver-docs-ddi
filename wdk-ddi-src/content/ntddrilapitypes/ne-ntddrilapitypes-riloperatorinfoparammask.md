---
UID: NE:ntddrilapitypes.RILOPERATORINFOPARAMMASK
title: RILOPERATORINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riloperatorinfoparammask.htm
old-project: netvista
ms.assetid: 5ea7bf77-2069-4335-862e-7f805f3a7491
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILOPERATORINFOPARAMMASK, RILOPERATORINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_OI_ALL, RIL_PARAM_OI_NAMES, RIL_PARAM_OI_STATUS, netvista.riloperatorinfoparammask, ntddrilapitypes/RILOPERATORINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_OI_ALL, ntddrilapitypes/RIL_PARAM_OI_NAMES, ntddrilapitypes/RIL_PARAM_OI_STATUS
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
-	RILOPERATORINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILOPERATORINFOPARAMMASK
---

# RILOPERATORINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILOPERATORINFOPARAMMASK { 
  RIL_PARAM_OI_STATUS,
  RIL_PARAM_OI_NAMES,
  RIL_PARAM_OI_ALL
} RILOPERATORINFOPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_OI_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_OI_INDEX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_OI_NAMES</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_OI_STATUS</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |