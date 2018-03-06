---
UID: NE:rilapitypes.RILUICCSLOTSTATE
title: RILUICCSLOTSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccslotstate_2.htm
old-project: netvista
ms.assetid: 472f7354-4b51-4fac-857e-d93083f160e8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILUICCSLOTSTATE, RILUICCSLOTSTATE enumeration [Network Drivers Starting with Windows Vista], RIL_UICCSLOT_ACTIVE, RIL_UICCSLOT_EMPTY, RIL_UICCSLOT_ERROR, RIL_UICCSLOT_MAX, RIL_UICCSLOT_NOT_READY, RIL_UICCSLOT_OFF, netvista.riluiccslotstate_2, rilapitypes/RILUICCSLOTSTATE, rilapitypes/RIL_UICCSLOT_ACTIVE, rilapitypes/RIL_UICCSLOT_EMPTY, rilapitypes/RIL_UICCSLOT_ERROR, rilapitypes/RIL_UICCSLOT_MAX, rilapitypes/RIL_UICCSLOT_NOT_READY, rilapitypes/RIL_UICCSLOT_OFF
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
-	RILUICCSLOTSTATE
product: Windows
targetos: Windows
req.typenames: RILUICCSLOTSTATE
req.product: Windows 10 or later.
---

# RILUICCSLOTSTATE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUICCSLOTSTATE { 
  RIL_UICCSLOT_OFF,
  RIL_UICCSLOT_EMPTY,
  RIL_UICCSLOT_NOT_READY,
  RIL_UICCSLOT_ACTIVE,
  RIL_UICCSLOT_ERROR,
  RIL_UICCSLOT_MAX
} RILUICCSLOTSTATE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_UICCSLOT_ACTIVE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCSLOT_EMPTY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCSLOT_ERROR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCSLOT_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCSLOT_NOT_READY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCSLOT_OFF</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_UICCSLOT_OFF_EMPTY</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |