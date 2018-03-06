---
UID: NE:rilapitypes.RILSUBADDRESSPARAMMASK
title: RILSUBADDRESSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsubaddressparammask_2.htm
old-project: netvista
ms.assetid: ef802d35-2ca6-4fe2-9f3b-e2d1e91b8500
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILSUBADDRESSPARAMMASK, RILSUBADDRESSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_SA_ALL, RIL_PARAM_SA_SUBADDRESS, netvista.rilsubaddressparammask_2, rilapitypes/RILSUBADDRESSPARAMMASK, rilapitypes/RIL_PARAM_SA_ALL, rilapitypes/RIL_PARAM_SA_SUBADDRESS
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
-	RILSUBADDRESSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILSUBADDRESSPARAMMASK
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |