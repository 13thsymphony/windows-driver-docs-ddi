---
UID: NE:ntddrilapitypes.RILACCESSTECHNOLOGYPARAMMASK
title: RILACCESSTECHNOLOGYPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilaccesstechnologyparammask.htm
old-project: netvista
ms.assetid: 58589d8c-f58c-4cb4-8f8e-0021f423efdf
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILACCESSTECHNOLOGYPARAMMASK, RILACCESSTECHNOLOGYPARAMMASK enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_PARAM_ACCTECH_SYSTEMKIND, RIL_PARAM_ACCTECH_SYSTEMKIND, netvista.rilaccesstechnologyparammask, RILACCESSTECHNOLOGYPARAMMASK, ntddrilapitypes/RIL_PARAM_ACCTECH_ALL, RIL_PARAM_ACCTECH_ALL
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
-	RILACCESSTECHNOLOGYPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILACCESSTECHNOLOGYPARAMMASK
---

# RILACCESSTECHNOLOGYPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILACCESSTECHNOLOGYPARAMMASK { 
  RIL_PARAM_ACCTECH_SYSTEMKIND,
  RIL_PARAM_ACCTECH_ALL
} RILACCESSTECHNOLOGYPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_ACCTECH_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_ACCTECH_SYSTEMKIND</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_ACCTECH_SYSTEMTYPE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |