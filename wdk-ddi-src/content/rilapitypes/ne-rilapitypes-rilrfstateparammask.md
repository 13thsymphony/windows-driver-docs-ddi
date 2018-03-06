---
UID: NE:rilapitypes.RILRFSTATEPARAMMASK
title: RILRFSTATEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrfstateparammask_2.htm
old-project: netvista
ms.assetid: 075c61aa-b091-4616-810b-f39ad40d2777
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILRFSTATEPARAMMASK, RILRFSTATEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_RFSTATE_ALL, RIL_PARAM_RFSTATE_RFDATA, RIL_PARAM_RFSTATE_RFDATASIZE, RIL_PARAM_RFSTATE_RFSTATE, netvista.rilrfstateparammask_2, rilapitypes/RILRFSTATEPARAMMASK, rilapitypes/RIL_PARAM_RFSTATE_ALL, rilapitypes/RIL_PARAM_RFSTATE_RFDATA, rilapitypes/RIL_PARAM_RFSTATE_RFDATASIZE, rilapitypes/RIL_PARAM_RFSTATE_RFSTATE
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
-	RILRFSTATEPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILRFSTATEPARAMMASK
req.product: Windows 10 or later.
---

# RILRFSTATEPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILRFSTATEPARAMMASK { 
  RIL_PARAM_RFSTATE_RFSTATE,
  RIL_PARAM_RFSTATE_RFDATASIZE,
  RIL_PARAM_RFSTATE_RFDATA,
  RIL_PARAM_RFSTATE_ALL
} RILRFSTATEPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_RFSTATE_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_RFSTATE_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_RFSTATE_RFDATA</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_RFSTATE_RFDATASIZE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_RFSTATE_RFSTATE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |