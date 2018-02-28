---
UID: NE:rilapitypes.RILIMSSUBSCRIBETYPE
title: RILIMSSUBSCRIBETYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimssubscribetype_2.htm
old-project: netvista
ms.assetid: 84b2de56-55f9-471c-8d32-84fe1365dfbf
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILIMSSUBSCRIBETYPE, RILIMSSUBSCRIBETYPE enumeration [Network Drivers Starting with Windows Vista], RIL_IMSSUBSCRIBETYPE_CONFERENCE, RIL_IMSSUBSCRIBETYPE_MAX, RIL_IMSSUBSCRIBETYPE_MWI, netvista.rilimssubscribetype_2, rilapitypes/RILIMSSUBSCRIBETYPE, rilapitypes/RIL_IMSSUBSCRIBETYPE_CONFERENCE, rilapitypes/RIL_IMSSUBSCRIBETYPE_MAX, rilapitypes/RIL_IMSSUBSCRIBETYPE_MWI
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
-	RILIMSSUBSCRIBETYPE
product: Windows
targetos: Windows
req.typenames: RILIMSSUBSCRIBETYPE
req.product: Windows 10 or later.
---

# RILIMSSUBSCRIBETYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILIMSSUBSCRIBETYPE { 
  RIL_IMSSUBSCRIBETYPE_MWI,
  RIL_IMSSUBSCRIBETYPE_CONFERENCE,
  RIL_IMSSUBSCRIBETYPE_MAX
} RILIMSSUBSCRIBETYPE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_IMSSUBSCRIBETYPE_CONFERENCE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMSSUBSCRIBETYPE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMSSUBSCRIBETYPE_MWI</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMSSUBSCRIBETYPE_REG</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |