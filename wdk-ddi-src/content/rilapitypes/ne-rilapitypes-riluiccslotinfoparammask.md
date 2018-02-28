---
UID: NE:rilapitypes.RILUICCSLOTINFOPARAMMASK
title: RILUICCSLOTINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccslotinfoparammask_2.htm
old-project: netvista
ms.assetid: 003c888b-5935-460d-8b89-13f4ab69dc85
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILUICCSLOTINFOPARAMMASK, RILUICCSLOTINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_SLOTINFO_ALL, RIL_PARAM_SLOTINFO_SLOTSTATE, netvista.riluiccslotinfoparammask_2, rilapitypes/RILUICCSLOTINFOPARAMMASK, rilapitypes/RIL_PARAM_SLOTINFO_ALL, rilapitypes/RIL_PARAM_SLOTINFO_SLOTSTATE
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
-	RILUICCSLOTINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUICCSLOTINFOPARAMMASK
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |