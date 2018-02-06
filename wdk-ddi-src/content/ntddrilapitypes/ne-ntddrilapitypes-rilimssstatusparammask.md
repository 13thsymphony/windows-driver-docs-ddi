---
UID: NE:ntddrilapitypes.RILIMSSSTATUSPARAMMASK
title: RILIMSSSTATUSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimssstatusparammask.htm
old-project: netvista
ms.assetid: bc31d252-eb1d-492c-ae2b-c6c7a8509685
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PARAM_IMSSTATUS_SMSSUPPORTEDFORMAT, ntddrilapitypes/RILIMSSSTATUSPARAMMASK, ntddrilapitypes/RIL_PARAM_IMSSTATUS_AVAILABLESERVICES, netvista.rilimssstatusparammask, RIL_PARAM_IMSSTATUS_ALL, RIL_PARAM_IMSSTATUS_SERVINGDOMAIN, RILIMSSSTATUSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_PARAM_IMSSTATUS_HUICCAPP, ntddrilapitypes/RIL_PARAM_IMSSTATUS_SMSSUPPORTEDFORMAT, ntddrilapitypes/RIL_PARAM_IMSSTATUS_SYSTEMTYPE, RILIMSSSTATUSPARAMMASK, RIL_PARAM_IMSSTATUS_AVAILABLESERVICES, RIL_PARAM_IMSSTATUS_HUICCAPP, ntddrilapitypes/RIL_PARAM_IMSSTATUS_ALL, RIL_PARAM_IMSSTATUS_SYSTEMTYPE, ntddrilapitypes/RIL_PARAM_IMSSTATUS_SERVINGDOMAIN
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
-	RILIMSSSTATUSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILIMSSSTATUSPARAMMASK
---

# RILIMSSSTATUSPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILIMSSSTATUSPARAMMASK { 
  RIL_PARAM_IMSSTATUS_HUICCAPP,
  RIL_PARAM_IMSSTATUS_AVAILABLESERVICES,
  RIL_PARAM_IMSSTATUS_SMSSUPPORTEDFORMAT,
  RIL_PARAM_IMSSTATUS_SERVINGDOMAIN,
  RIL_PARAM_IMSSTATUS_SYSTEMTYPE,
  RIL_PARAM_IMSSTATUS_ALL
} RILIMSSSTATUSPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_IMSSTATUS_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_IMSSTATUS_AVAILABLESERVICES</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_IMSSTATUS_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_IMSSTATUS_HUICCAPP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_IMSSTATUS_SERVINGDOMAIN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_IMSSTATUS_SMSSUPPORTEDFORMAT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_IMSSTATUS_SYSTEMTYPE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |