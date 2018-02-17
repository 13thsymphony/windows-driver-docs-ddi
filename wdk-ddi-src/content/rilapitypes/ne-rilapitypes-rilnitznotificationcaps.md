---
UID: NE:rilapitypes.RILNITZNOTIFICATIONCAPS
title: RILNITZNOTIFICATIONCAPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnitznotificationcaps_2.htm
old-project: netvista
ms.assetid: 74f62528-57ec-4142-a1b0-0d779e9d0ca0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_CAPS_NITZ_MAX, netvista.rilnitznotificationcaps_2, rilapitypes/RILNITZNOTIFICATIONCAPS, RILNITZNOTIFICATIONCAPS, RILNITZNOTIFICATIONCAPS enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_CAPS_NITZ_ENABLED, rilapitypes/RIL_CAPS_NITZ_MAX, RIL_CAPS_NITZ_ENABLED
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILNITZNOTIFICATIONCAPS
product: Windows
targetos: Windows
req.typenames: RILNITZNOTIFICATIONCAPS
req.product: Windows 10 or later.
---

# RILNITZNOTIFICATIONCAPS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILNITZNOTIFICATIONCAPS { 
  RIL_CAPS_NITZ_ENABLED,
  RIL_CAPS_NITZ_MAX
} RILNITZNOTIFICATIONCAPS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_CAPS_NITZ_DISABLED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_NITZ_ENABLED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_NITZ_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |