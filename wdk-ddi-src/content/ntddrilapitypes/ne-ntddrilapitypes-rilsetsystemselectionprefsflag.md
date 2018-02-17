---
UID: NE:ntddrilapitypes.RILSETSYSTEMSELECTIONPREFSFLAG
title: RILSETSYSTEMSELECTIONPREFSFLAG
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetsystemselectionprefsflag.htm
old-project: netvista
ms.assetid: 081f4a23-43d8-4ad4-806c-1b6322e057d5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_SSSPFLAG_APPLYIMMEDIATELY, RILSETSYSTEMSELECTIONPREFSFLAG enumeration [Network Drivers Starting with Windows Vista], RILSETSYSTEMSELECTIONPREFSFLAG, ntddrilapitypes/RIL_SSSPFLAG_ALL, ntddrilapitypes/RIL_SSSPFLAG_APPLYIMMEDIATELY, RIL_SSSPFLAG_ENFORCESCAN, ntddrilapitypes/RIL_SSSPFLAG_ENFORCESCAN, RIL_SSSPFLAG_ALL, ntddrilapitypes/RILSETSYSTEMSELECTIONPREFSFLAG, netvista.rilsetsystemselectionprefsflag
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
-	RILSETSYSTEMSELECTIONPREFSFLAG
product: Windows
targetos: Windows
req.typenames: RILSETSYSTEMSELECTIONPREFSFLAG
---

# RILSETSYSTEMSELECTIONPREFSFLAG Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSETSYSTEMSELECTIONPREFSFLAG { 
  RIL_SSSPFLAG_APPLYIMMEDIATELY,
  RIL_SSSPFLAG_ENFORCESCAN,
  RIL_SSSPFLAG_ALL
} RILSETSYSTEMSELECTIONPREFSFLAG;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_SSSPFLAG_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SSSPFLAG_APPLYIMMEDIATELY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SSSPFLAG_ENFORCESCAN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SSSPFLAG_NONE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |