---
UID: NE:rilapitypes.RILEXCHANGEUICCAPDURESPONSEPARAMMASK
title: RILEXCHANGEUICCAPDURESPONSEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexchangeuiccapduresponseparammask.htm
old-project: netvista
ms.assetid: 24daa47b-993c-49ee-b4e2-462cd7570f3c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILEXCHANGEUICCAPDURESPONSEPARAMMASK, RILEXCHANGEUICCAPDURESPONSEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_EUAR_ALL, RIL_PARAM_EUAR_RESPONSEAPDU, netvista.rilexchangeuiccapduresponseparammask, ntddrilapitypes/RILEXCHANGEUICCAPDURESPONSEPARAMMASK, ntddrilapitypes/RIL_PARAM_EUAR_ALL, ntddrilapitypes/RIL_PARAM_EUAR_RESPONSEAPDU
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
-	RILEXCHANGEUICCAPDURESPONSEPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILEXCHANGEUICCAPDURESPONSEPARAMMASK
req.product: Windows 10 or later.
---

# RILEXCHANGEUICCAPDURESPONSEPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILEXCHANGEUICCAPDURESPONSEPARAMMASK { 
  RIL_PARAM_EUAR_RESPONSEAPDU,
  RIL_PARAM_EUAR_ALL
} RILEXCHANGEUICCAPDURESPONSEPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_EUAR_RESPONSEAPDULENGTH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_EUAR_RESPONSEAPDU</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_EUAR_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |