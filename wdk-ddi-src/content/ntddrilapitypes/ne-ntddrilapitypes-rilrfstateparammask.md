---
UID: NE:ntddrilapitypes.RILRFSTATEPARAMMASK
title: RILRFSTATEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrfstateparammask.htm
old-project: netvista
ms.assetid: 53cd2444-fda7-4e1f-b2d3-23ab20955a0e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILRFSTATEPARAMMASK, RIL_PARAM_RFSTATE_RFSTATE, RIL_PARAM_RFSTATE_RFDATASIZE, netvista.rilrfstateparammask, ntddrilapitypes/RIL_PARAM_RFSTATE_RFSTATE, RIL_PARAM_RFSTATE_ALL, ntddrilapitypes/RILRFSTATEPARAMMASK, ntddrilapitypes/RIL_PARAM_RFSTATE_ALL, ntddrilapitypes/RIL_PARAM_RFSTATE_RFDATASIZE, RIL_PARAM_RFSTATE_RFDATA, ntddrilapitypes/RIL_PARAM_RFSTATE_RFDATA, RILRFSTATEPARAMMASK enumeration [Network Drivers Starting with Windows Vista]
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
-	RILRFSTATEPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILRFSTATEPARAMMASK
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
| **Header** | ntddrilapitypes.h |