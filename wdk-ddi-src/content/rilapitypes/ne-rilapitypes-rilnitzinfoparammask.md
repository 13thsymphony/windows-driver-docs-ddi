---
UID: NE:rilapitypes.RILNITZINFOPARAMMASK
title: RILNITZINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnitzinfoparammask.htm
old-project: netvista
ms.assetid: bdf1505f-2a84-48a3-9534-df83237ab7bb
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILNITZINFOPARAMMASK, RILNITZINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_NITZ_ALL, RIL_PARAM_NITZ_DAYLIGHTSAVINGOFFSET, RIL_PARAM_NITZ_SYSTEMTIME, RIL_PARAM_NITZ_SYSTEMTYPE, RIL_PARAM_NITZ_TIMEZONEOFFSET, netvista.rilnitzinfoparammask, ntddrilapitypes/RILNITZINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_NITZ_ALL, ntddrilapitypes/RIL_PARAM_NITZ_DAYLIGHTSAVINGOFFSET, ntddrilapitypes/RIL_PARAM_NITZ_SYSTEMTIME, ntddrilapitypes/RIL_PARAM_NITZ_SYSTEMTYPE, ntddrilapitypes/RIL_PARAM_NITZ_TIMEZONEOFFSET
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
-	RILNITZINFOPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILNITZINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILNITZINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILNITZINFOPARAMMASK {
  RIL_PARAM_NITZ_EXECUTOR              ,
  RIL_PARAM_NITZ_TIMEZONEOFFSET        ,
  RIL_PARAM_NITZ_DAYLIGHTSAVINGOFFSET  ,
  RIL_PARAM_NITZ_SYSTEMTIME            ,
  RIL_PARAM_NITZ_SYSTEMTYPE            ,
  RIL_PARAM_NITZ_ALL
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_NITZ_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_NITZ_TIMEZONEOFFSET</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_NITZ_DAYLIGHTSAVINGOFFSET</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_NITZ_SYSTEMTIME</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_NITZ_SYSTEMTYPE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_NITZ_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |