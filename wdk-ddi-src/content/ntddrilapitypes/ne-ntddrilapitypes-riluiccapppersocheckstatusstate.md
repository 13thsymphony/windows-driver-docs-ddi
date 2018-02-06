---
UID: NE:ntddrilapitypes.RILUICCAPPPERSOCHECKSTATUSSTATE
title: RILUICCAPPPERSOCHECKSTATUSSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccapppersocheckstatusstate.htm
old-project: netvista
ms.assetid: d41d5559-b9ec-4ae5-b658-8f75e8af13e4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILUICCAPPPERSOCHECKSTATUSSTATE, netvista.riluiccapppersocheckstatusstate, ntddrilapitypes/RIL_PERSOCHECKSTATE_FAIL, RIL_PERSOCHECKSTATE_FAIL, RIL_PERSOCHECKSTATE_MAX, ntddrilapitypes/RILUICCAPPPERSOCHECKSTATUSSTATE, RIL_PERSOCHECKSTATE_PASS, ntddrilapitypes/RIL_PERSOCHECKSTATE_MAX, RILUICCAPPPERSOCHECKSTATUSSTATE enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_PERSOCHECKSTATE_PASS
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
-	RILUICCAPPPERSOCHECKSTATUSSTATE
product: Windows
targetos: Windows
req.typenames: RILUICCAPPPERSOCHECKSTATUSSTATE
---

# RILUICCAPPPERSOCHECKSTATUSSTATE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUICCAPPPERSOCHECKSTATUSSTATE { 
  RIL_PERSOCHECKSTATE_PASS,
  RIL_PERSOCHECKSTATE_FAIL,
  RIL_PERSOCHECKSTATE_MAX
} RILUICCAPPPERSOCHECKSTATUSSTATE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PERSOCHECKSTATE_FAIL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PERSOCHECKSTATE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PERSOCHECKSTATE_NOTREADY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PERSOCHECKSTATE_PASS</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |