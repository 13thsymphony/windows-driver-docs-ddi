---
UID: NE:ntddrilapitypes.RILTDSCDMAKIND
title: RILTDSCDMAKIND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltdscdmakind.htm
old-project: netvista
ms.assetid: 61b5d7f8-bd45-448b-b7a1-3e52909a63cb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_TDSCDMAKIND_DC_HSPAPLUS, RIL_TDSCDMAKIND_HSPAPLUS, ntddrilapitypes/RIL_TDSCDMAKIND_HSUPA, netvista.riltdscdmakind, ntddrilapitypes/RILTDSCDMAKIND, RILTDSCDMAKIND enumeration [Network Drivers Starting with Windows Vista], RIL_TDSCDMAKIND_MAX, RILTDSCDMAKIND, ntddrilapitypes/RIL_TDSCDMAKIND_HSPAPLUS, ntddrilapitypes/RIL_TDSCDMAKIND_MAX, RIL_TDSCDMAKIND_DC_HSPAPLUS, ntddrilapitypes/RIL_TDSCDMAKIND_HSDPA, RIL_TDSCDMAKIND_HSUPA, RIL_TDSCDMAKIND_HSDPA
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
-	RILTDSCDMAKIND
product: Windows
targetos: Windows
req.typenames: RILTDSCDMAKIND
---

# RILTDSCDMAKIND Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILTDSCDMAKIND { 
  RIL_TDSCDMAKIND_HSDPA,
  RIL_TDSCDMAKIND_HSUPA,
  RIL_TDSCDMAKIND_HSPAPLUS,
  RIL_TDSCDMAKIND_DC_HSPAPLUS,
  RIL_TDSCDMAKIND_MAX
} RILTDSCDMAKIND;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_TDSCDMAKIND_DC_HSPAPLUS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_TDSCDMAKIND_HSDPA</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_TDSCDMAKIND_HSPAPLUS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_TDSCDMAKIND_HSUPA</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_TDSCDMAKIND_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_TDSCDMAKIND_UMTS</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |