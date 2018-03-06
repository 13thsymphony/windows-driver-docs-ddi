---
UID: NE:rilapitypes.RILGSMMNMRPARAMMASK
title: RILGSMMNMRPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgsmmnmrparammask_2.htm
old-project: netvista
ms.assetid: 9e58bd61-9cb7-40fb-a6e5-1e8a8d428774
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILGSMMNMRPARAMMASK, RILGSMMNMRPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_GSMNMR_ALL, RIL_PARAM_GSMNMR_ARFCN, RIL_PARAM_GSMNMR_BSID, RIL_PARAM_GSMNMR_CELLID, RIL_PARAM_GSMNMR_LAC, RIL_PARAM_GSMNMR_MNC, RIL_PARAM_GSMNMR_RXLEVEL, netvista.rilgsmmnmrparammask_2, rilapitypes/RILGSMMNMRPARAMMASK, rilapitypes/RIL_PARAM_GSMNMR_ALL, rilapitypes/RIL_PARAM_GSMNMR_ARFCN, rilapitypes/RIL_PARAM_GSMNMR_BSID, rilapitypes/RIL_PARAM_GSMNMR_CELLID, rilapitypes/RIL_PARAM_GSMNMR_LAC, rilapitypes/RIL_PARAM_GSMNMR_MNC, rilapitypes/RIL_PARAM_GSMNMR_RXLEVEL
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
-	RILGSMMNMRPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILGSMMNMRPARAMMASK
req.product: Windows 10 or later.
---

# RILGSMMNMRPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILGSMMNMRPARAMMASK { 
  RIL_PARAM_GSMNMR_MNC,
  RIL_PARAM_GSMNMR_LAC,
  RIL_PARAM_GSMNMR_CELLID,
  RIL_PARAM_GSMNMR_ARFCN,
  RIL_PARAM_GSMNMR_BSID,
  RIL_PARAM_GSMNMR_RXLEVEL,
  RIL_PARAM_GSMNMR_ALL
} RILGSMMNMRPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_GSMNMR_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_GSMNMR_ARFCN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_GSMNMR_BSID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_GSMNMR_CELLID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_GSMNMR_LAC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_GSMNMR_MCC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_GSMNMR_MNC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_GSMNMR_RXLEVEL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |