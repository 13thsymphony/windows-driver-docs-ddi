---
UID: NE:ntddrilapitypes.RILSYSTEMCAPS
title: RILSYSTEMCAPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemcaps.htm
old-project: netvista
ms.assetid: ed0ecb71-22b4-4387-8d5a-4d6fd2c7047e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSYSTEMCAPS, RIL_SYSTEMCAPS_ALL, ntddrilapitypes/RILSYSTEMCAPS, ntddrilapitypes/RIL_SYSTEMCAPS_ALL, ntddrilapitypes/RIL_SYSTEMCAPS_VOICEDATA, RIL_SYSTEMCAPS_VOICEDATA, netvista.rilsystemcaps, RILSYSTEMCAPS enumeration [Network Drivers Starting with Windows Vista]
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
-	RILSYSTEMCAPS
product: Windows
targetos: Windows
req.typenames: RILSYSTEMCAPS
---

# RILSYSTEMCAPS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSYSTEMCAPS { 
  RIL_SYSTEMCAPS_VOICEDATA,
  RIL_SYSTEMCAPS_ALL
} RILSYSTEMCAPS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_SYSTEMCAPS_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMCAPS_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SYSTEMCAPS_VOICEDATA</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |