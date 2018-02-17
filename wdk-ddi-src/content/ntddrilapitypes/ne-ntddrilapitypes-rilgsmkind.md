---
UID: NE:ntddrilapitypes.RILGSMKIND
title: RILGSMKIND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgsmkind.htm
old-project: netvista
ms.assetid: ad88382b-bfb0-46c4-9db7-9adb1ee074a4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_GSMKIND_MAX, RILGSMKIND, RIL_GSMKIND_GPRS, ntddrilapitypes/RILGSMKIND, ntddrilapitypes/RIL_GSMKIND_GPRS, ntddrilapitypes/RIL_GSMKIND_EDGE, netvista.rilgsmkind, RIL_GSMKIND_MAX, RILGSMKIND enumeration [Network Drivers Starting with Windows Vista], RIL_GSMKIND_EDGE
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
-	RILGSMKIND
product: Windows
targetos: Windows
req.typenames: RILGSMKIND
---

# RILGSMKIND Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILGSMKIND { 
  RIL_GSMKIND_GPRS,
  RIL_GSMKIND_EDGE,
  RIL_GSMKIND_MAX
} RILGSMKIND;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_GSMKIND_EDGE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GSMKIND_GPRS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GSMKIND_GSM</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GSMKIND_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |