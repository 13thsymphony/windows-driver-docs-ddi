---
UID: NE:ntddrilapitypes.RILRADIOPRESENCE
title: RILRADIOPRESENCE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiopresence.htm
old-project: netvista
ms.assetid: de67cf2e-1dd8-4b01-9a60-b8a2a01d326b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILRADIOPRESENCE, RILRADIOPRESENCE enumeration [Network Drivers Starting with Windows Vista], RIL_RADIOPRESENCE_PRESENT, RIL_RADIOPRESENCE_MAX, ntddrilapitypes/RIL_RADIOPRESENCE_PRESENT, ntddrilapitypes/RILRADIOPRESENCE, netvista.rilradiopresence, ntddrilapitypes/RIL_RADIOPRESENCE_MAX
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
-	RILRADIOPRESENCE
product: Windows
targetos: Windows
req.typenames: RILRADIOPRESENCE
---

# RILRADIOPRESENCE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILRADIOPRESENCE { 
  RIL_RADIOPRESENCE_PRESENT,
  RIL_RADIOPRESENCE_MAX
} RILRADIOPRESENCE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_RADIOPRESENCE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RADIOPRESENCE_NOTPRESENT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RADIOPRESENCE_PRESENT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |