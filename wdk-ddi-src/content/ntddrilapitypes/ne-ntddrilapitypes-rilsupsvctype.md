---
UID: NE:ntddrilapitypes.RILSUPSVCTYPE
title: RILSUPSVCTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupsvctype.htm
old-project: netvista
ms.assetid: 3d9415f7-cc28-4e45-8d88-b8693aa57116
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILSUPSVCTYPE, RILSUPSVCTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_SUPSVCTYPE_CLIP, RIL_SUPSVCTYPE_CLIR, RIL_SUPSVCTYPE_CNAP, RIL_SUPSVCTYPE_COLP, RIL_SUPSVCTYPE_COLR, RIL_SUPSVCTYPE_MAX, netvista.rilsupsvctype, ntddrilapitypes/RILSUPSVCTYPE, ntddrilapitypes/RIL_SUPSVCTYPE_CLIP, ntddrilapitypes/RIL_SUPSVCTYPE_CLIR, ntddrilapitypes/RIL_SUPSVCTYPE_CNAP, ntddrilapitypes/RIL_SUPSVCTYPE_COLP, ntddrilapitypes/RIL_SUPSVCTYPE_COLR, ntddrilapitypes/RIL_SUPSVCTYPE_MAX
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
-	RILSUPSVCTYPE
product:
- Windows
targetos: Windows
req.typenames: RILSUPSVCTYPE
---

# RILSUPSVCTYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILSUPSVCTYPE {
  RIL_SUPSVCTYPE_CALLWAITING  ,
  RIL_SUPSVCTYPE_CLIP         ,
  RIL_SUPSVCTYPE_CLIR         ,
  RIL_SUPSVCTYPE_COLP         ,
  RIL_SUPSVCTYPE_COLR         ,
  RIL_SUPSVCTYPE_CNAP         ,
  RIL_SUPSVCTYPE_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_SUPSVCTYPE_CALLWAITING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUPSVCTYPE_CLIP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUPSVCTYPE_CLIR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUPSVCTYPE_COLP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUPSVCTYPE_COLR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUPSVCTYPE_CNAP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUPSVCTYPE_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |