---
UID: NE:ntddrilapitypes.RILMSGDCSFLAGS
title: RILMSGDCSFLAGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcsflags.htm
old-project: netvista
ms.assetid: 9c69d290-0cc6-4444-b9cb-a9555526e9ed
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILMSGDCSFLAGS, RILMSGDCSFLAGS enumeration [Network Drivers Starting with Windows Vista], RIL_DCSFLAG_ALL, RIL_DCSFLAG_COMPRESSED, RIL_DCSFLAG_DISCARD, RIL_DCSFLAG_INDICATIONACTIVE, netvista.rilmsgdcsflags, ntddrilapitypes/RILMSGDCSFLAGS, ntddrilapitypes/RIL_DCSFLAG_ALL, ntddrilapitypes/RIL_DCSFLAG_COMPRESSED, ntddrilapitypes/RIL_DCSFLAG_DISCARD, ntddrilapitypes/RIL_DCSFLAG_INDICATIONACTIVE
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
-	RILMSGDCSFLAGS
product: Windows
targetos: Windows
req.typenames: RILMSGDCSFLAGS
---

# RILMSGDCSFLAGS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGDCSFLAGS { 
  RIL_DCSFLAG_COMPRESSED,
  RIL_DCSFLAG_INDICATIONACTIVE,
  RIL_DCSFLAG_DISCARD,
  RIL_DCSFLAG_ALL
} RILMSGDCSFLAGS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_DCSFLAG_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSFLAG_COMPRESSED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSFLAG_DISCARD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSFLAG_INDICATIONACTIVE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSFLAG_NONE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |