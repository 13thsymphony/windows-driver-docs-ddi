---
UID: NE:ntddrilapitypes.RILALPHAIDENTIFIDERTYPE
title: RILALPHAIDENTIFIDERTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilalphaidentifidertype.htm
old-project: netvista
ms.assetid: e7be6f28-b6f0-4b95-9145-abbb98e7f5a5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILALPHAIDENTIFIDERTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_ALPHAIDENTIFIERTYPE_PRESENT, ntddrilapitypes/RIL_ALPHAIDENTIFIERTYPE_NOTPRESENT, ntddrilapitypes/RIL_ALPHAIDENTIFIERTYPE_MAX, RIL_ALPHAIDENTIFIERTYPE_MAX, ntddrilapitypes/RILALPHAIDENTIFIDERTYPE, ntddrilapitypes/RIL_ALPHAIDENTIFIERTYPE_PRESENT, netvista.rilalphaidentifidertype, RILALPHAIDENTIFIDERTYPE, RIL_ALPHAIDENTIFIERTYPE_NOTPRESENT
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
-	RILALPHAIDENTIFIDERTYPE
product: Windows
targetos: Windows
req.typenames: RILALPHAIDENTIFIDERTYPE
---

# RILALPHAIDENTIFIDERTYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILALPHAIDENTIFIDERTYPE { 
  RIL_ALPHAIDENTIFIERTYPE_PRESENT,
  RIL_ALPHAIDENTIFIERTYPE_NOTPRESENT,
  RIL_ALPHAIDENTIFIERTYPE_MAX
} RILALPHAIDENTIFIDERTYPE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_ALPHAIDENTIFIERTYPE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ALPHAIDENTIFIERTYPE_NOTPRESENT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ALPHAIDENTIFIERTYPE_PRESENT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ALPHAIDENTIFIERTYPE_UNKNOWN</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |