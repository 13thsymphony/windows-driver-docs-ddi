---
UID: NE:ntddrilapitypes.RILMODEMRESETSTATE
title: RILMODEMRESETSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmodemresetstate.htm
old-project: netvista
ms.assetid: 4069ded7-95d7-46c2-a4a7-a360482c7b7d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILMODEMRESETSTATE, RILMODEMRESETSTATE enumeration [Network Drivers Starting with Windows Vista], RIL_MODEMRESETSTATE_FAILED, RIL_MODEMRESETSTATE_MAX, RIL_MODEMRESETSTATE_RECOVERED, netvista.rilmodemresetstate, ntddrilapitypes/RILMODEMRESETSTATE, ntddrilapitypes/RIL_MODEMRESETSTATE_FAILED, ntddrilapitypes/RIL_MODEMRESETSTATE_MAX, ntddrilapitypes/RIL_MODEMRESETSTATE_RECOVERED
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
-	RILMODEMRESETSTATE
product: Windows
targetos: Windows
req.typenames: RILMODEMRESETSTATE
---

# RILMODEMRESETSTATE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMODEMRESETSTATE { 
  RIL_MODEMRESETSTATE_RECOVERED,
  RIL_MODEMRESETSTATE_FAILED,
  RIL_MODEMRESETSTATE_MAX
} RILMODEMRESETSTATE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_MODEMRESETSTATE_FAILED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MODEMRESETSTATE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MODEMRESETSTATE_RECOVERED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MODEMRESETSTATE_STARTED</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |