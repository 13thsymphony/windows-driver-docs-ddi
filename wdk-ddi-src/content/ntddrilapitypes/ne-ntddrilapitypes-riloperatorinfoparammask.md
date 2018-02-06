---
UID: NE:ntddrilapitypes.RILOPERATORINFOPARAMMASK
title: RILOPERATORINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riloperatorinfoparammask.htm
old-project: netvista
ms.assetid: 5ea7bf77-2069-4335-862e-7f805f3a7491
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PARAM_OI_ALL, RILOPERATORINFOPARAMMASK, RILOPERATORINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_OI_NAMES, ntddrilapitypes/RIL_PARAM_OI_NAMES, ntddrilapitypes/RIL_PARAM_OI_STATUS, RIL_PARAM_OI_STATUS, ntddrilapitypes/RIL_PARAM_OI_ALL, netvista.riloperatorinfoparammask, ntddrilapitypes/RILOPERATORINFOPARAMMASK
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
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