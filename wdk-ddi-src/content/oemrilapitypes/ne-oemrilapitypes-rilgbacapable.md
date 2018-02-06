---
UID: NE:oemrilapitypes.RILGBACAPABLE
title: RILGBACAPABLE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgbacapable.htm
old-project: netvista
ms.assetid: c1acc574-6e9e-40a1-8892-00572fcc545c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILGBACAPABLE enumeration [Network Drivers Starting with Windows Vista], RIL_GBA_UNKNOWN, netvista.rilgbacapable, oemrilapitypes/RIL_GBA_NOT_SUPPORTED, RIL_GBA_U_SUPPORTED, RIL_GBA_ME_SUPPORTED, RIL_GBA_NOT_SUPPORTED, RILGBACAPABLE, oemrilapitypes/RILGBACAPABLE, oemrilapitypes/RIL_GBA_UNKNOWN, oemrilapitypes/RIL_GBA_U_SUPPORTED, oemrilapitypes/RIL_GBA_ME_SUPPORTED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: oemrilapitypes.h
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
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	oemrilapitypes.h
apiname:
-	RILGBACAPABLE
product: Windows
targetos: Windows
req.typenames: RILGBACAPABLE
---

# RILGBACAPABLE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILGBACAPABLE { 
  RIL_GBA_UNKNOWN,
  RIL_GBA_NOT_SUPPORTED,
  RIL_GBA_ME_SUPPORTED,
  RIL_GBA_U_SUPPORTED
} RILGBACAPABLE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_GBA_ME_SUPPORTED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GBA_NOT_SUPPORTED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GBA_U_SUPPORTED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GBA_UNKNOWN</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | oemrilapitypes.h |