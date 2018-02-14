---
UID: NE:rilapitypes.RILNITZINFOPARAMMASK
title: RILNITZINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnitzinfoparammask_2.htm
old-project: netvista
ms.assetid: c9ee5373-53eb-4356-8969-4d7bfea13779
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILNITZINFOPARAMMASK, rilapitypes/RIL_PARAM_NITZ_SYSTEMTYPE, netvista.rilnitzinfoparammask_2, RIL_PARAM_NITZ_SYSTEMTIME, RIL_PARAM_NITZ_TIMEZONEOFFSET, rilapitypes/RILNITZINFOPARAMMASK, RIL_PARAM_NITZ_DAYLIGHTSAVINGOFFSET, rilapitypes/RIL_PARAM_NITZ_DAYLIGHTSAVINGOFFSET, RIL_PARAM_NITZ_SYSTEMTYPE, RIL_PARAM_NITZ_ALL, RILNITZINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_PARAM_NITZ_ALL, rilapitypes/RIL_PARAM_NITZ_SYSTEMTIME, rilapitypes/RIL_PARAM_NITZ_TIMEZONEOFFSET
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILNITZINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILNITZINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILNITZINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILNITZINFOPARAMMASK { 
  RIL_PARAM_NITZ_TIMEZONEOFFSET,
  RIL_PARAM_NITZ_DAYLIGHTSAVINGOFFSET,
  RIL_PARAM_NITZ_SYSTEMTIME,
  RIL_PARAM_NITZ_SYSTEMTYPE,
  RIL_PARAM_NITZ_ALL
} RILNITZINFOPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_NITZ_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_NITZ_DAYLIGHTSAVINGOFFSET</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_NITZ_EXECUTOR</td>
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
                    <td>RIL_PARAM_NITZ_TIMEZONEOFFSET</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |