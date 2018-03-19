---
UID: NE:rilapitypes.RILCALLWAITINGINFOPARAMMASK
title: RILCALLWAITINGINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallwaitinginfoparammask.htm
old-project: netvista
ms.assetid: 18fa3b00-8da7-4c83-a340-1515caffda01
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILCALLWAITINGINFOPARAMMASK, RILCALLWAITINGINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_CWI_ALL, RIL_PARAM_CWI_CALLERINFO, RIL_PARAM_CWI_CALLTYPE, netvista.rilcallwaitinginfoparammask, ntddrilapitypes/RILCALLWAITINGINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_CWI_ALL, ntddrilapitypes/RIL_PARAM_CWI_CALLERINFO, ntddrilapitypes/RIL_PARAM_CWI_CALLTYPE
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
-	RILCALLWAITINGINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILCALLWAITINGINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILCALLWAITINGINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLWAITINGINFOPARAMMASK { 
  RIL_PARAM_CWI_CALLTYPE,
  RIL_PARAM_CWI_CALLERINFO,
  RIL_PARAM_CWI_ALL
} RILCALLWAITINGINFOPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_CWI_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CWI_CALLTYPE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CWI_CALLERINFO</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CWI_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |