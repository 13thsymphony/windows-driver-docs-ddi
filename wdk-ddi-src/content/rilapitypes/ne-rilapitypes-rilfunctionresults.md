---
UID: NE:rilapitypes.RILFUNCTIONRESULTS
title: RILFUNCTIONRESULTS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilfunctionresults.htm
old-project: netvista
ms.assetid: 9a2b3bdd-4955-4293-b4e7-65da20b0d369
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILFUNCTIONRESULTS, RILFUNCTIONRESULTS enumeration [Network Drivers Starting with Windows Vista], RIL_RESULT_ERROR, netvista.rilfunctionresults, ntddrilapitypes/RILFUNCTIONRESULTS, ntddrilapitypes/RIL_RESULT_ERROR
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
-	RILFUNCTIONRESULTS
product: Windows
targetos: Windows
req.typenames: RILFUNCTIONRESULTS
req.product: Windows 10 or later.
---

# RILFUNCTIONRESULTS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILFUNCTIONRESULTS { 
  RIL_RESULT_ERROR
} RILFUNCTIONRESULTS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_RESULT_OK</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RESULT_ERROR</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |