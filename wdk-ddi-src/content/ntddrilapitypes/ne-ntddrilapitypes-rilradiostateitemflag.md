---
UID: NE:ntddrilapitypes.RILRADIOSTATEITEMFLAG
title: RILRADIOSTATEITEMFLAG
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostateitemflag.htm
old-project: netvista
ms.assetid: dcbd0b16-4960-4cc1-b76b-6d971ba6a192
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILRADIOSTATEITEMFLAG, RILRADIOSTATEITEMFLAG enumeration [Network Drivers Starting with Windows Vista], RIL_RADIOSTATE_ITEMFLAG_USE_BYTEARRAY, RIL_RADIOSTATE_ITEMFLAG_USE_INTARRAY, RIL_RADIOSTATE_ITEMFLAG_USE_MAX, RIL_RADIOSTATE_ITEMFLAG_USE_UINTARRAY, RIL_RADIOSTATE_ITEMFLAG_USE_UINTVAL, RIL_RADIOSTATE_ITEMFLAG_USE_WSZVAL, netvista.rilradiostateitemflag, ntddrilapitypes/RILRADIOSTATEITEMFLAG, ntddrilapitypes/RIL_RADIOSTATE_ITEMFLAG_USE_BYTEARRAY, ntddrilapitypes/RIL_RADIOSTATE_ITEMFLAG_USE_INTARRAY, ntddrilapitypes/RIL_RADIOSTATE_ITEMFLAG_USE_MAX, ntddrilapitypes/RIL_RADIOSTATE_ITEMFLAG_USE_UINTARRAY, ntddrilapitypes/RIL_RADIOSTATE_ITEMFLAG_USE_UINTVAL, ntddrilapitypes/RIL_RADIOSTATE_ITEMFLAG_USE_WSZVAL
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILRADIOSTATEITEMFLAG
product: Windows
targetos: Windows
req.typenames: RILRADIOSTATEITEMFLAG
---

# RILRADIOSTATEITEMFLAG Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILRADIOSTATEITEMFLAG { 
  RIL_RADIOSTATE_ITEMFLAG_USE_UINTVAL,
  RIL_RADIOSTATE_ITEMFLAG_USE_WSZVAL,
  RIL_RADIOSTATE_ITEMFLAG_USE_INTARRAY,
  RIL_RADIOSTATE_ITEMFLAG_USE_UINTARRAY,
  RIL_RADIOSTATE_ITEMFLAG_USE_BYTEARRAY,
  RIL_RADIOSTATE_ITEMFLAG_USE_MAX
} RILRADIOSTATEITEMFLAG;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_RADIOSTATE_ITEMFLAG_USE_BYTEARRAY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RADIOSTATE_ITEMFLAG_USE_INTARRAY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RADIOSTATE_ITEMFLAG_USE_INTVAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RADIOSTATE_ITEMFLAG_USE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RADIOSTATE_ITEMFLAG_USE_UINTARRAY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RADIOSTATE_ITEMFLAG_USE_UINTVAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RADIOSTATE_ITEMFLAG_USE_WSZVAL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |