---
UID: NE:ntddrilapitypes.RILUICCCARDINFOPARAMMASK
title: RILUICCCARDINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicccardinfoparammask.htm
old-project: netvista
ms.assetid: e206ed8b-89c3-4503-a4c7-57d29c9c00ff
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_PARAM_CARDINFO_APPINFO, ntddrilapitypes/RIL_PARAM_CARDINFO_ALL, netvista.riluicccardinfoparammask, ntddrilapitypes/RIL_PARAM_CARDINFO_ICCID, ntddrilapitypes/RILUICCCARDINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_CARDINFO_APPINFO, RILUICCCARDINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_CARDINFO_NUMAPPS, ntddrilapitypes/RIL_PARAM_CARDINFO_NUMAPPS, RIL_PARAM_CARDINFO_ALL, RIL_PARAM_CARDINFO_ICCID, RILUICCCARDINFOPARAMMASK
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
-	RILUICCCARDINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUICCCARDINFOPARAMMASK
---

# RILUICCCARDINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUICCCARDINFOPARAMMASK { 
  RIL_PARAM_CARDINFO_ICCID,
  RIL_PARAM_CARDINFO_NUMAPPS,
  RIL_PARAM_CARDINFO_APPINFO,
  RIL_PARAM_CARDINFO_ALL
} RILUICCCARDINFOPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_CARDINFO_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CARDINFO_APPINFO</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CARDINFO_ICCID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CARDINFO_ISVIRTUAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CARDINFO_NUMAPPS</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |