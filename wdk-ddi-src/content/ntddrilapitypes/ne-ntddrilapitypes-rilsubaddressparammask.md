---
UID: NE:ntddrilapitypes.RILSUBADDRESSPARAMMASK
title: RILSUBADDRESSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsubaddressparammask.htm
old-project: netvista
ms.assetid: 12684719-f263-4909-bcb7-b75381cc7e43
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILSUBADDRESSPARAMMASK, RILSUBADDRESSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_SA_ALL, RIL_PARAM_SA_SUBADDRESS, netvista.rilsubaddressparammask, ntddrilapitypes/RILSUBADDRESSPARAMMASK, ntddrilapitypes/RIL_PARAM_SA_ALL, ntddrilapitypes/RIL_PARAM_SA_SUBADDRESS
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
-	RILSUBADDRESSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILSUBADDRESSPARAMMASK
---

# RILSUBADDRESSPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSUBADDRESSPARAMMASK { 
  RIL_PARAM_SA_SUBADDRESS,
  RIL_PARAM_SA_ALL
} RILSUBADDRESSPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_SA_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SA_SUBADDRESS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SA_TYPE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |