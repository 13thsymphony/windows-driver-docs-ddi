---
UID: NE:ntddrilapitypes.RILIMSSUBSCRIBETYPE
title: RILIMSSUBSCRIBETYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimssubscribetype.htm
old-project: netvista
ms.assetid: 347b42c1-7585-471c-af42-44218da48fa3
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILIMSSUBSCRIBETYPE, RILIMSSUBSCRIBETYPE enumeration [Network Drivers Starting with Windows Vista], RIL_IMSSUBSCRIBETYPE_CONFERENCE, RIL_IMSSUBSCRIBETYPE_MAX, RIL_IMSSUBSCRIBETYPE_MWI, netvista.rilimssubscribetype, ntddrilapitypes/RILIMSSUBSCRIBETYPE, ntddrilapitypes/RIL_IMSSUBSCRIBETYPE_CONFERENCE, ntddrilapitypes/RIL_IMSSUBSCRIBETYPE_MAX, ntddrilapitypes/RIL_IMSSUBSCRIBETYPE_MWI
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
-	RILIMSSUBSCRIBETYPE
product: Windows
targetos: Windows
req.typenames: RILIMSSUBSCRIBETYPE
---

# RILIMSSUBSCRIBETYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILIMSSUBSCRIBETYPE {
  RIL_IMSSUBSCRIBETYPE_REG         ,
  RIL_IMSSUBSCRIBETYPE_MWI         ,
  RIL_IMSSUBSCRIBETYPE_CONFERENCE  ,
  RIL_IMSSUBSCRIBETYPE_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_IMSSUBSCRIBETYPE_REG</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMSSUBSCRIBETYPE_MWI</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMSSUBSCRIBETYPE_CONFERENCE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMSSUBSCRIBETYPE_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |