---
UID: NE:ntddrilapitypes.RILUICCSLOTINFOPARAMMASK
title: RILUICCSLOTINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccslotinfoparammask.htm
old-project: netvista
ms.assetid: f99fc76e-a569-4a7e-9f8d-3f604ccfa6a3
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PARAM_SLOTINFO_SLOTSTATE, ntddrilapitypes/RILUICCSLOTINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_SLOTINFO_SLOTSTATE, RILUICCSLOTINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RILUICCSLOTINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_SLOTINFO_ALL, RIL_PARAM_SLOTINFO_ALL, netvista.riluiccslotinfoparammask
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
-	RILUICCSLOTINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUICCSLOTINFOPARAMMASK
---

# RILUICCSLOTINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUICCSLOTINFOPARAMMASK { 
  RIL_PARAM_SLOTINFO_SLOTSTATE,
  RIL_PARAM_SLOTINFO_ALL
} RILUICCSLOTINFOPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_SLOTINFO_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SLOTINFO_NUMSLOTS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SLOTINFO_SLOTSTATE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |