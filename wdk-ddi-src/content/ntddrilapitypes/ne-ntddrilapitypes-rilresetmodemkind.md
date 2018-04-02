---
UID: NE:ntddrilapitypes.RILRESETMODEMKIND
title: RILRESETMODEMKIND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilresetmodemkind.htm
old-project: netvista
ms.assetid: 4eb97a4f-dd95-4fd4-8315-efcb446f56cd
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILRESETMODEMKIND, RILRESETMODEMKIND enumeration [Network Drivers Starting with Windows Vista], RIL_RESETMODEMKIND_ABRUPT, RIL_RESETMODEMKIND_MAX, netvista.rilresetmodemkind, ntddrilapitypes/RILRESETMODEMKIND, ntddrilapitypes/RIL_RESETMODEMKIND_ABRUPT, ntddrilapitypes/RIL_RESETMODEMKIND_MAX
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
-	RILRESETMODEMKIND
product: Windows
targetos: Windows
req.typenames: RILRESETMODEMKIND
---

# RILRESETMODEMKIND Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILRESETMODEMKIND {
  RIL_RESETMODEMKIND_NORMAL  ,
  RIL_RESETMODEMKIND_ABRUPT  ,
  RIL_RESETMODEMKIND_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_RESETMODEMKIND_NORMAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RESETMODEMKIND_ABRUPT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RESETMODEMKIND_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |