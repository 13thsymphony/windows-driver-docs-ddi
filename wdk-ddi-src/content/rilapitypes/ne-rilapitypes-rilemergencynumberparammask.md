---
UID: NE:rilapitypes.RILEMERGENCYNUMBERPARAMMASK
title: RILEMERGENCYNUMBERPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencynumberparammask.htm
old-project: netvista
ms.assetid: e8365373-130b-485c-9117-89be6153be52
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILEMERGENCYNUMBERPARAMMASK, RILEMERGENCYNUMBERPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_ENUM_ALL, RIL_PARAM_ENUM_CATEGORY, RIL_PARAM_ENUM_NUMBER, RIL_PARAM_ENUM_UICC, netvista.rilemergencynumberparammask, ntddrilapitypes/RILEMERGENCYNUMBERPARAMMASK, ntddrilapitypes/RIL_PARAM_ENUM_ALL, ntddrilapitypes/RIL_PARAM_ENUM_CATEGORY, ntddrilapitypes/RIL_PARAM_ENUM_NUMBER, ntddrilapitypes/RIL_PARAM_ENUM_UICC
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
-	RILEMERGENCYNUMBERPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILEMERGENCYNUMBERPARAMMASK
req.product: Windows 10 or later.
---

# RILEMERGENCYNUMBERPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILEMERGENCYNUMBERPARAMMASK { 
  RIL_PARAM_ENUM_UICC,
  RIL_PARAM_ENUM_CATEGORY,
  RIL_PARAM_ENUM_NUMBER,
  RIL_PARAM_ENUM_ALL
} RILEMERGENCYNUMBERPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_ENUM_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_ENUM_CATEGORY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_ENUM_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_ENUM_NUMBER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_ENUM_UICC</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |