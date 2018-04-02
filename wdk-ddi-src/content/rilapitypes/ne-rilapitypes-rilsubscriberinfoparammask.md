---
UID: NE:rilapitypes.RILSUBSCRIBERINFOPARAMMASK
title: RILSUBSCRIBERINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsubscriberinfoparammask_2.htm
old-project: netvista
ms.assetid: fe8b08d4-4cc1-49cd-b0f8-29e8b198b0d1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILSUBSCRIBERINFOPARAMMASK, RILSUBSCRIBERINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_SI_ALL, RIL_PARAM_SI_DESCRIPTION, RIL_PARAM_SI_SERVICE, netvista.rilsubscriberinfoparammask_2, rilapitypes/RILSUBSCRIBERINFOPARAMMASK, rilapitypes/RIL_PARAM_SI_ALL, rilapitypes/RIL_PARAM_SI_DESCRIPTION, rilapitypes/RIL_PARAM_SI_SERVICE
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
-	RILSUBSCRIBERINFOPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILSUBSCRIBERINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILSUBSCRIBERINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSUBSCRIBERINFOPARAMMASK { 
  RIL_PARAM_SI_DESCRIPTION,
  RIL_PARAM_SI_SERVICE,
  RIL_PARAM_SI_ALL
} RILSUBSCRIBERINFOPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_SI_ADDRESS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SI_DESCRIPTION</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SI_SERVICE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SI_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |