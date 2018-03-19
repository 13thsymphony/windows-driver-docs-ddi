---
UID: NE:rilapitypes.RILALPHAIDENTIFIDERTYPE
title: RILALPHAIDENTIFIDERTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilalphaidentifidertype.htm
old-project: netvista
ms.assetid: e7be6f28-b6f0-4b95-9145-abbb98e7f5a5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILALPHAIDENTIFIDERTYPE, RILALPHAIDENTIFIDERTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_ALPHAIDENTIFIERTYPE_MAX, RIL_ALPHAIDENTIFIERTYPE_NOTPRESENT, RIL_ALPHAIDENTIFIERTYPE_PRESENT, netvista.rilalphaidentifidertype, ntddrilapitypes/RILALPHAIDENTIFIDERTYPE, ntddrilapitypes/RIL_ALPHAIDENTIFIERTYPE_MAX, ntddrilapitypes/RIL_ALPHAIDENTIFIERTYPE_NOTPRESENT, ntddrilapitypes/RIL_ALPHAIDENTIFIERTYPE_PRESENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
-	RILALPHAIDENTIFIDERTYPE
product: Windows
targetos: Windows
req.typenames: RILALPHAIDENTIFIDERTYPE
req.product: Windows 10 or later.
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
                    <td>RIL_ALPHAIDENTIFIERTYPE_UNKNOWN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ALPHAIDENTIFIERTYPE_PRESENT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ALPHAIDENTIFIERTYPE_NOTPRESENT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ALPHAIDENTIFIERTYPE_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |