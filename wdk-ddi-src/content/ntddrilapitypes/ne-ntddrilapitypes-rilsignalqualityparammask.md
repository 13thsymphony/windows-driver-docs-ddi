---
UID: NE:ntddrilapitypes.RILSIGNALQUALITYPARAMMASK
title: RILSIGNALQUALITYPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsignalqualityparammask.htm
old-project: netvista
ms.assetid: cf6727dc-e6f3-418e-bee4-e372dcc29a66
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILSIGNALQUALITYPARAMMASK, RILSIGNALQUALITYPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_SQ_ALL, RIL_PARAM_SQ_NUMSIGNALBARS, RIL_PARAM_SQ_SIGNALSTRENGTH, RIL_PARAM_SQ_SNR, RIL_PARAM_SQ_SYSTEMTYPE, netvista.rilsignalqualityparammask, ntddrilapitypes/RILSIGNALQUALITYPARAMMASK, ntddrilapitypes/RIL_PARAM_SQ_ALL, ntddrilapitypes/RIL_PARAM_SQ_NUMSIGNALBARS, ntddrilapitypes/RIL_PARAM_SQ_SIGNALSTRENGTH, ntddrilapitypes/RIL_PARAM_SQ_SNR, ntddrilapitypes/RIL_PARAM_SQ_SYSTEMTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
-	RILSIGNALQUALITYPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILSIGNALQUALITYPARAMMASK
---

# RILSIGNALQUALITYPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSIGNALQUALITYPARAMMASK { 
  RIL_PARAM_SQ_SYSTEMTYPE,
  RIL_PARAM_SQ_NUMSIGNALBARS,
  RIL_PARAM_SQ_SIGNALSTRENGTH,
  RIL_PARAM_SQ_SNR,
  RIL_PARAM_SQ_ALL
} RILSIGNALQUALITYPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_SQ_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SQ_SYSTEMTYPE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SQ_NUMSIGNALBARS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SQ_SIGNALSTRENGTH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SQ_SNR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SQ_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |