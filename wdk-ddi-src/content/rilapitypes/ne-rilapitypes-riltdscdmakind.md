---
UID: NE:rilapitypes.RILTDSCDMAKIND
title: RILTDSCDMAKIND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltdscdmakind_2.htm
old-project: netvista
ms.assetid: ff6c4459-dd3e-43f6-aa41-a2e82221394e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILTDSCDMAKIND, RILTDSCDMAKIND enumeration [Network Drivers Starting with Windows Vista], RIL_TDSCDMAKIND_DC_HSPAPLUS, RIL_TDSCDMAKIND_HSDPA, RIL_TDSCDMAKIND_HSPAPLUS, RIL_TDSCDMAKIND_HSUPA, RIL_TDSCDMAKIND_MAX, netvista.riltdscdmakind_2, rilapitypes/RILTDSCDMAKIND, rilapitypes/RIL_TDSCDMAKIND_DC_HSPAPLUS, rilapitypes/RIL_TDSCDMAKIND_HSDPA, rilapitypes/RIL_TDSCDMAKIND_HSPAPLUS, rilapitypes/RIL_TDSCDMAKIND_HSUPA, rilapitypes/RIL_TDSCDMAKIND_MAX
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
-	RILTDSCDMAKIND
product: Windows
targetos: Windows
req.typenames: RILTDSCDMAKIND
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |