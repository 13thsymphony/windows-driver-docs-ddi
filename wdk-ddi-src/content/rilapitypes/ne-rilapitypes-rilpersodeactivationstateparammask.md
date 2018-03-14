---
UID: NE:rilapitypes.RILPERSODEACTIVATIONSTATEPARAMMASK
title: RILPERSODEACTIVATIONSTATEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpersodeactivationstateparammask.htm
old-project: netvista
ms.assetid: 11c4388b-5c0d-4133-9c68-059d1af5c2ca
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILPERSODEACTIVATIONSTATEPARAMMASK, RILPERSODEACTIVATIONSTATEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_PDS_ALL, RIL_PARAM_PDS_CK_ATTEMPTS, RIL_PARAM_PDS_PUK_ATTEMPTS, netvista.rilpersodeactivationstateparammask, ntddrilapitypes/RILPERSODEACTIVATIONSTATEPARAMMASK, ntddrilapitypes/RIL_PARAM_PDS_ALL, ntddrilapitypes/RIL_PARAM_PDS_CK_ATTEMPTS, ntddrilapitypes/RIL_PARAM_PDS_PUK_ATTEMPTS
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
-	RILPERSODEACTIVATIONSTATEPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILPERSODEACTIVATIONSTATEPARAMMASK
req.product: Windows 10 or later.
---

# RILPERSODEACTIVATIONSTATEPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILPERSODEACTIVATIONSTATEPARAMMASK { 
  RIL_PARAM_PDS_CK_ATTEMPTS,
  RIL_PARAM_PDS_PUK_ATTEMPTS,
  RIL_PARAM_PDS_ALL
} RILPERSODEACTIVATIONSTATEPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_PDS_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_PDS_CK_ATTEMPTS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_PDS_PUK_ATTEMPTS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_PDS_STATE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |